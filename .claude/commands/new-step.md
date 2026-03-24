Crea un nuevo archivo Lua para un step del chatbot.

Los scripts se organizan por carpeta de cuenta. Cada cuenta tiene su propia subcarpeta dentro del repositorio.

**Flujo:**
1. Si $ARGUMENTS tiene formato `[cuenta]/[nombre]` (ej. `ccu/validar-otp`), usarlo directamente.
2. Si solo viene un nombre sin cuenta, preguntar a qué cuenta pertenece antes de crear el archivo.
3. Si no hay argumento, preguntar cuenta y nombre.

El archivo se crea en `[cuenta]/[nombre].lua` (kebab-case).

Si la carpeta de la cuenta no existe, crearla.

El archivo debe estar vacío o con estructura mínima según lo que el usuario describa.
Recuerda las reglas del proyecto: sin `require`, `Workflow.branch()` siempre hardcodeado, librerías ya precargadas.

Luego pregunta qué lógica necesita el step.
