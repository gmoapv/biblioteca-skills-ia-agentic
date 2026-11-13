# Rúbrica de idoneidad para IA

Cada paso del proceso se puntúa en cuatro dimensiones, de 0 a 5. La suma da el puntaje de 0 a 20.

## Dimensiones

| Dimensión | 5 | 3 | 1 | 0 |
|---|---|---|---|---|
| **T. Tipo de tarea** | Regla fija (copiar, mover, calcular) o tarea de lenguaje (resumir, clasificar, redactar, extraer) | Requiere juicio, pero con criterios que se pueden escribir | Requiere juicio experto difícil de explicar, o negociar con personas | Es física o presencial |
| **E. Estandarización del insumo** | Llega siempre en el mismo formato | Tiene variaciones manejables | Es muy variable o desordenado | No existe o no está definido |
| **R. Tolerancia al error** | Un error es barato y fácil de detectar | Un error cuesta algo, pero se puede revisar antes de que tenga efecto | Un error afecta a personas, dinero o temas legales | Un error es irreversible o crítico |
| **D. Datos disponibles** | Digitales y accesibles sin restricciones | Digitales, pero confidenciales o con permisos (hay que anonimizar o pedir acceso) | En papel o dispersos | No están disponibles |

Los valores 2 y 4 se usan para casos intermedios.

## De puntaje a semáforo

| Puntaje | Etiqueta | Semáforo |
|---|---|---|
| 15–20 | SÍ | 🟢 Recomendable |
| 9–14 | CONDICIONADA | 🟡 Recomendable con control humano |
| 0–8 | NO | 🔴 No por ahora |

**Reglas que mandan sobre el puntaje:**
1. Si **cualquier** dimensión vale 0 → 🔴, sin importar la suma.
2. Si **R vale 1** → como máximo 🟡, y la decisión final la toma una persona.
3. Si la tarea es una **decisión crítica** (contratar, sancionar, aprobar pagos, diagnosticar) → tipo de uso "Apoyo a la decisión", nunca automatización.

## Tipo de uso según la tarea
- Resumir, clasificar, redactar, extraer → IA generativa: `Asistente` o `Automatización parcial`.
- Copiar, mover, enviar, exportar, calcular con fórmulas → `Automatización tradicional` (programas, macros, flujos sin IA).
- Revisar, comparar, detectar anomalías → `Control de calidad`.
- Decidir algo importante → `Apoyo a la decisión`.

## Justificación y control humano
Cada fila de la evaluación lleva una justificación de una línea que explica el puntaje más bajo. Los pasos 🟡 llevan además un control humano concreto: **quién** revisa **qué** y **en qué momento** (por ejemplo, "la analista revisa las filas marcadas antes de calcular indicadores").
