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

- **`Debug.print()`** muestra el mensaje directamente en el chat del chatbot (WhatsApp/LINE), no es solo un log interno. Usarlo intencionalmente para comunicar estado al usuario/operador.
- Al recibir un step nuevo, **crear inmediatamente el archivo `.lua`** con nombre kebab-case descriptivo, o preguntar el nombre si no es obvio.

---

## Variables de almacenamiento: Context / Profile / Global

Tres namespaces con las mismas 4 operaciones cada uno:

| Operación               | Descripción                       |
| ----------------------- | --------------------------------- |
| `.get('nombre')`        | Obtiene el valor de la variable   |
| `.set('nombre', valor)` | Asigna un valor                   |
| `.check('nombre')`      | Devuelve `true`/`false` si existe |
| `.delete('nombre')`     | Elimina la variable               |

### Context

Variables de **sesión** — se borran cuando termina la conversación.

```lua
Context.set('cart', cartData)
Context.get('userId')
Context.check('canBuy')
Context.delete('canBuy')
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
Global.get('VAT')
Global.get('cdpToken')
Global.get('accountName')
Global.get('CommonsCloudFunctionsBaseUrl')
Global.get('maxUserLimit')
Global.get('maxStoreLimit')
```

### Variables con valor por defecto conocido

- `Context.get('userId')` — número de teléfono del usuario (WhatsApp) o ID de cuenta (LINE)

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
-- NOTA: response.data es userdata. Para manipular como tabla: JSON.decode(response.dataStr)
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
CDP.contactGet(phone)
CDP.contactUpsert({ phone, name, channels, attributes?, stores? })
CDP.contactRegister({ channelId, storeCode, reason, registrationSource })
-- Requiere CDP.init() antes de usar cualquier función
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
Debug.print(value)          -- Muestra en el chat del chatbot
JSON.decode(jsonString)
JSON.encode(value)
```

### Estándar Lua

- `math` — abs, ceil, floor, pi, random, sqrt
- `table` — insert, remove
- `string` — operaciones estándar Lua

---

## Patrones comunes

### Patrón fetch → transform → store

```lua
local response = Commerce.cartGet()
if response.status == "ok" then
    Context.set('cart', response.data)
else
    Workflow.branch(nodeIdError)
end
```

### Validación con branch

```lua
if condicion then
    Workflow.branch(nodeIdExito)
else
    Workflow.branch(nodeIdError)
end
```

### Inicializar Commerce

```lua
local storefrontName = Global.get('storefrontName')
local adminUrl = Global.get('storefrontAdminUrl')
Commerce.init(storefrontName, adminUrl)
```

---

## Estructura de carpetas por cuenta

Los scripts se organizan en subcarpetas por cuenta (cliente). Cada cuenta tiene su propia carpeta:

```
luaScripts/
├── ccu/
├── suntory/
├── italcol/
└── (otras cuentas)
```

Al crear un nuevo step, siempre hay que definir a qué cuenta pertenece. El archivo se crea dentro de la carpeta correspondiente.

---

## Cómo pedir un nuevo script

- "Nuevo step: [descripción]" → Claude pregunta la cuenta y crea el archivo en `[cuenta]/[nombre].lua`.
- "Pasarte código" → Claude recibe el código existente como base para modificar.
- Los archivos se nombran con kebab-case descriptivo: `cliente-validar-compra.lua`

