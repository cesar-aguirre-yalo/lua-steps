# luaScripts — Contexto del Proyecto

## ¿Qué es esto?

Scripts Lua independientes que se ejecutan como **steps (pasos) de un flujo de chatbot** (WhatsApp o LINE). Cada archivo es un fragmento aislado sin relación con los demás — no hay imports entre scripts ni estado compartido en código.

---

## Reglas estrictas

- **Nunca importar librerías** (`require` está prohibido). Las librerías disponibles ya están precargadas por el runtime.
- Cada script es autocontenido. No puede llamar funciones definidas en otro archivo.
- Los scripts se ejecutan en un entorno Lua ajustado (no es Lua estándar completo).
- **`Workflow.branch()` siempre con el número hardcodeado**, nunca por variable. La función de exportar/importar del sistema falla si el node ID está en una variable y no lo detecta correctamente.

  ```lua
  -- CORRECTO
  Workflow.branch(333)

  -- MAL — rompe el export/import
  local nextNode = 333
  Workflow.branch(nextNode)
  ```

- **`Debug.print()`** muestra el mensaje directamente en el chat del chatbot (WhatsApp/LINE). Solo usarlo si el usuario lo pide explícitamente.
- **Todo el código en inglés**: variables, comentarios, keys de Context/Profile, mensajes de error.
- **Arrays en Lua:** el índice inicial puede ser `0` o `1` dependiendo del origen del dato (librería, runtime, GraphQL). Si un loop no recorre nada o da nil, verificar con Debug.print desde qué índice empieza el array.
- Al recibir un step nuevo, **crear inmediatamente el archivo `.lua`** con nombre kebab-case descriptivo, o preguntar el nombre si no es obvio.

---

## Variables de almacenamiento: Context / Profile / Global

Tres namespaces con las mismas 4 operaciones cada uno:

| Operación               | Descripción                       |
| ----------------------- | --------------------------------- |
| `.get('nombre')`        | Obtiene el valor de la variable   |
| `.set('nombre', valor)` | Asigna un valor                   |
| `.check('nombre')`      | Devuelve `true` si la variable **existe**, independientemente de su valor |
| `.delete('nombre')`     | Elimina la variable               |

### Context

Variables de **sesión** — se borran cuando termina la conversación.

```lua
Context.set('cart', cartData)  -- acepta tablas directamente, nunca usar JSON.encode
Context.get('userId')
Context.check('canBuy')        -- true si existe, aunque el valor sea false
Context.delete('canBuy')
```

**Releer objetos con JSON.decode:** Al acceder a campos anidados de un objeto guardado en Context, siempre releer con `JSON.decode` para evitar errores de userdata:

```lua
Context.set('customer', customer)
local customer = JSON.decode(Context.get('customer'))
local code = customer.customFields.__businessSecurityCode  -- funciona
```

**Flags booleanos con Context.check:** Como `check` devuelve `true` si la variable existe (incluso si vale `false`), el patrón correcto para flags es `delete` + `set(true)`:

```lua
Context.delete('isOwner')           -- limpiar antes
for i = 1, #stores do
    if stores[i].role == 'owner' then
        Context.set('isOwner', true) -- solo setear si cumple
        break
    end
end

-- En otro step:
if Context.check('isOwner') then    -- true solo si fue seteado
    Workflow.branch(480)
else
    Workflow.branch(20)
end
```

### Profile

Variables que **persisten por usuario** (número de teléfono / LINE ID).

```lua
Profile.set('lastCustomerCode', code)
Profile.get('lastCustomerCode')
Profile.check('existDataCustomer')
Profile.delete('registration')
```

### Global

Variables de **configuración a nivel proyecto** — solo lectura en general.

```lua
Global.get('storefrontName')
Global.get('storefrontUserUrl')     -- URL GraphQL sesión de usuario
Global.get('storefrontAdminUrl')    -- URL GraphQL backoffice
Global.get('VAT')
Global.get('cdpToken')
Global.get('accountName')
Global.get('CommonsCloudFunctionsBaseUrl')
Global.get('maxUserLimit')
Global.get('maxStoreLimit')
```

### Variables de contexto con valor conocido

- `Context.get('userId')` — número de teléfono del usuario (WhatsApp) o ID de cuenta (LINE)
- `Context.get('userMessage')` — último mensaje enviado por el usuario

---

## Librerías precargadas disponibles

Referencia completa: https://www.notion.so/yalo/Yalo-Studio-Manual-507b0fd3d45f4de69b53fbcaf70ef58f

### `HTTP`

```lua
HTTP.get(url, headers?) -> HttpResponse
HTTP.post(url, body?, headers?) -> HttpResponse
HTTP.put(url, body?, headers?) -> HttpResponse
HTTP.patch(url, body?, headers?) -> HttpResponse
HTTP.delete(url, headers?) -> HttpResponse
-- HttpResponse: { data, dataStr, status, statusText, headers, config }
-- response.data — objeto parseado. El primer nivel es accesible, pero subobjetos anidados son userdata
-- response.dataStr — string del body (solo el contenido, sin status/headers)
```

### `Commerce`

```lua
Commerce.init(storefrontName, url?) -> headlessResponse
Commerce.sessionCreate(type, value)   -- type: 'code' | 'phoneNumber'
Commerce.cartGet()
Commerce.orderCreate()
Commerce.orderConfirm(orderId)
Commerce.sessionExpire()
Commerce.updateCustomer(objectId, data)
Commerce.sessionUpdateData(data)
-- headlessResponse: { status: "ok"|"error", data: {...} }
-- Otros métodos: checkoutRuleAccept/Get/Set, orderCancel, orderCheck, orderGet,
--   cartEmpty, cartRemove, cartAdd, search, phoneNumberAdd/Remove,
--   addressUpdate, catalog, productGet, storeNearby, storefrontGet
```

### `CDP`

```lua
CDP.init({ accountName = string })
  -> { success, data: { accountName } }

CDP.contactGet(phone)
  -> { success, data: { contact: { _id, code, name, attributes, channels }, stores, totalStores } }
  -- Nota: docs oficiales no muestran stores/totalStores pero sí vienen en práctica

CDP.contactUpsert({ phone, name, channels, attributes?, stores? })
  -> { success, data: { _id, code, name, attributes } }

CDP.contactRegister({ channelId, storeCode, reason, registrationSource })
  -- formato de respuesta no documentado

-- Requiere CDP.init() antes de usar cualquier función
-- Devuelve userdata — guardar en Context y releer con JSON.decode antes de iterar campos anidados
```

### `SalesDesk`

```lua
SalesDesk.init({ xAuthToken, xInstance, xUserId, xBotId })
SalesDesk.businessHours(departmentName)
SalesDesk.updateContact({ token, name, email?, customFields? })
SalesDesk.updateRoom({ roomId, contactId?, tags? })
SalesDesk.closeChat({ roomId, phone, comment?, tags? })
SalesDesk.transferToQueue({ userSessionId, departmentName, username })
SalesDesk.transferAfterNotification({ contactId, templateId, userSessionId, username, comment?, tags?, openChat? })
SalesDesk.transferToDepartmentOrAgent({ roomId, departmentName?, username?, agentId?, comment?, tags? })
SalesDesk.getRoom({ roomId })
SalesDesk.getAgent({ agentId? | email? | contactId? })
```

### `Reminder`

```lua
Reminder.init({ queueName? })                               -- default: yalo-common-queue
Reminder.create(stepId, delay, queueName?)                  -- delay: 20, "15m", "30s", "2h", timestamp
Reminder.createWithContext(stepId, delay, contextData, queueName?)
Reminder.cancel(taskName)
```

### `String`

```lua
String.cleanText(text)                              -- Elimina diacríticos y normaliza
String.onlyNumbers(text)                            -- Extrae solo números
String.split(text, separator?)
String.encodeURI(text)
String.formatCurrency(value, locale?, currency?)
String.truncateWordsWithinLimit(value, limit)
String.encodeBase64(value, encoding?)               -- Usar esto, no implementación manual
String.decodeBase64(text, encoding?)
```

### `CloudRun`

```lua
CloudRun.invokeFunction({ url, body?, headers?, method?, contextKey? }) -> { success, response, status }
-- Guarda respuesta en Context automáticamente
-- NO usar para funciones que retornen 401/403
```

### `Invoke` (AWS Lambda)

```lua
Invoke.cloudFunction(lambda, body) -> { success, payload }
-- body debe ser string: JSON.encode(data)
```

### `Input`

```lua
Input.match(type, expression, value?, options?) -> boolean
-- type: 'contains' | 'regex' | 'isEqualTo'
Input.intent(domain, message?) -> { status, message, confidence? }
Input.getMessage() -> { message, type, step }
Input.getProfile() -> { userId, name }
```

### `FAQ`

```lua
FAQ.searchQuestion(question, sheetId, config?) -> { success, singleMatch, multipleMatch, noMatch, matchQuestion, matchAnswer, faqs }
```

### `Location`

```lua
Location.stores(keyword, radius, placeType, address?) -> { success, places }
```

### `Schedule`

```lua
Schedule.message(stepId, delayInMinutes)   -- Envía mensaje tras delay, usuario queda en mismo step
Schedule.branch(stepId, delayInMinutes)    -- Redirige al step tras delay
```

### `BusinessHours`

```lua
BusinessHours.config({ timezone, monday, tuesday, wednesday, thursday, friday, saturday, sunday })
-- Valores de día: "09:00-17:00" o "closed"
-- Respuesta: { error, open }
```

### `Event`

```lua
Event.track(name, properties) -> EventPayload
```

### `OptIn`

```lua
OptIn.setAnswer(value)   -- true = aceptó T&Cs
```

### `Workflow` / `Debug` / `JSON`

```lua
Workflow.branch(nodeId)     -- ⚠️ siempre número hardcodeado
Debug.print(value)          -- Muestra en el chat del chatbot — solo si el usuario lo pide
JSON.decode(jsonString)
JSON.encode(value)
```

### Estándar Lua

- `math` — abs, ceil, floor, pi, random, sqrt
- `table` — insert, remove
- `string` — operaciones estándar Lua

---

## Patrones comunes

### Guardar siempre las respuestas en Context

Toda llamada HTTP, Commerce, CloudRun u otra función externa **debe guardarse en Context** antes de procesar. Sirve para debug en producción.

```lua
local response = HTTP.post(url, payload, headers)
Context.set('getOrdersResponse', response)
```

### Llamadas GraphQL (HTTP.post)

La URL viene siempre de `Global.get(...)`. El schema está en `.claude/graphql-admin-schema.md` y `.claude/graphql-user-schema.md` — leerlo antes de escribir una query.

**Estructura de respuesta:**
```
response.data.data.[queryName]   →  datos del resultado
response.dataStr                 →  '{"data":{"customers":[...]}}'  (sin status/headers)
```

Dos formas equivalentes de acceder a subobjetos sin errores de userdata:

**A — JSON.decode(response.dataStr):** convierte todo de una vez.
```lua
local response = HTTP.post(adminUrl, payload, { ['content-type'] = 'application/json' })
Context.set('getCustomersResponse', response)
local result = JSON.decode(response.dataStr)
local customer = result.data.customers[1]
local code = customer.customFields.__businessSecurityCode  -- funciona
```
> `dataStr` tiene estructura `{"data":{"customers":[...]}}` — path: `result.data.[queryName]`

**B — Guardar en Context y releer con JSON.decode:** patrón común en steps existentes.
```lua
local response = HTTP.post(adminUrl, payload, { ['content-type'] = 'application/json' })
Context.set('getCustomersResponse', response)
local customers = response.data.data.customers
Context.set('customer', customers[1])
local customer = JSON.decode(Context.get('customer'))
local code = customer.customFields.__businessSecurityCode  -- funciona
```

### Inicializar Commerce

```lua
local storefrontName = Global.get('storefrontName')
local userUrl = Global.get('storefrontUserUrl')
local adminUrl = Global.get('storefrontAdminUrl')
Commerce.init(storefrontName, userUrl, adminUrl)
```

### Patrón fetch → branch

```lua
local response = Commerce.cartGet()
Context.set('cartResponse', response)
if response.status == 'ok' then
    Context.set('cart', response.data)
    Workflow.branch(0) -- success
else
    Workflow.branch(0) -- error
end
```

---

## Referencia de schema GraphQL (Storefront)

Leer el archivo correspondiente **antes** de escribir cualquier query o mutación:

- `.claude/graphql-admin-schema.md` — operaciones de backoffice (usar con `storefrontAdminUrl`)
- `.claude/graphql-user-schema.md` — operaciones del flujo del chatbot (usar con `storefrontUserUrl`)

---

## Estructura de carpetas por cuenta

Los scripts se organizan en subcarpetas por cuenta (cliente). Al crear un nuevo step, siempre hay que definir a qué cuenta pertenece. Usar el comando `/new-step`.
