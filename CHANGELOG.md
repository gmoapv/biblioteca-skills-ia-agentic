# Registro de cambios

## 2.0.0 — 2026-11-13
### Agregado
- Skill `coordinador-automatizacion-ia`: recibe el encargo, elige el punto de entrada, ofrece las rutas, consolida los resultados en una sola tabla y hace una revisión final.
- `mapeo-de-procesos/formato-mapa-de-proceso.md`: formato común con el que las skills se pasan la información (Markdown con bloque JSON opcional).
- `mapeo-de-procesos/rubrica-idoneidad-ia.md`: rúbrica de cuatro dimensiones (tipo de tarea, estandarización, tolerancia al error, datos disponibles) para el puntaje de 0 a 20, con reglas de semáforo.
- `ejemplos/flujo-completo-informe-ventas.md`: caso de punta a punta con las dos rutas.
- Este registro de cambios.

### Cambiado
- Todo en español, incluidos los nombres de las skills y de las carpetas, en formato estándar de Agent Skills (minúsculas y guiones):
  `Work_Interpreter` → `mapeo-de-procesos`, `Prompt_Assistant` → `prompts-maestros`, `Proposal_Generator` → `fichas-de-desarrollo`.
- Descripciones reescritas para que digan cuándo usar cada skill (así se activan solas).
- `prompts-maestros` y `fichas-de-desarrollo` leen el formato común, agrupan pasos relacionados y saben qué hacer si no reciben un mapa.
- `fichas-de-desarrollo` agrega puntos de decisión, prueba y seguridad de los datos al plan.
- `mapeo-de-procesos` deja la pregunta de rutas al coordinador cuando trabaja dentro del flujo.
- Ejemplos reescritos con el formato completo (pasos, decisiones, puntajes y fases).
- README corregido: describe las dos rutas alternativas (antes decía que la cadena era lineal) y lo que entrega realmente cada skill.

### Corregido
- Erratas ("freshiere", "Ignora ignora") y emojis rotos en el README.

## 1.0.0 — 2026-02-16
- Versión inicial: Work Interpreter, Prompt Assistant y Proposal Generator.
