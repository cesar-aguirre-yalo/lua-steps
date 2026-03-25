Actualiza los schemas GraphQL del Storefront guardados en `.claude/`.

Los schemas están en:
- `.claude/graphql-admin-schema.md` — endpoint de staging: `https://storefront-admin.yalochat.dev/v3/admin/storefronts`
- `.claude/graphql-user-schema.md` — endpoint de staging: `https://storefront-user.yalochat.dev/v3/user/storefronts`

**Flujo por defecto:**
1. Pregunta al usuario si quiere usar los endpoints de staging ya configurados (opción por defecto) o proporcionar un schema manualmente.
2. Si elige staging, realiza una introspección GraphQL a cada endpoint con:
   ```
   POST [endpoint]
   Content-Type: application/json
   { "query": "{ __schema { types { name kind fields { name type { name kind ofType { name kind } } args { name type { name kind ofType { name kind } } } } } queryType { fields { name } } mutationType { fields { name } } } }" }
   ```
3. Compara el resultado con el contenido actual de los archivos `.md`.
4. Identifica queries/mutaciones nuevas, eliminadas, o con parámetros/tipos cambiados.
5. Actualiza los archivos `.md` afectados manteniendo el formato de tablas Markdown existente.
6. Si no hay cambios, informa que los schemas están al día.

**Formato de los archivos .md:**
Cada operación documenta nombre, tipo de retorno, y tabla de parámetros: Parameter, Type, Required, Default, Description.
Los tipos se documentan como secciones `####` con tabla: Field, Type, Deprecated, Description.