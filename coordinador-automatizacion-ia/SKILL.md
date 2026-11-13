---
name: coordinador-automatizacion-ia
description: "Coordina el flujo completo para llevar la IA a un trabajo o proceso: recibe el encargo, decide por dónde partir, encarga el mapa del proceso a mapeo-de-procesos, ofrece la ruta ágil (prompts-maestros), la técnica (fichas-de-desarrollo) o ambas, y consolida todo en un solo resultado revisado. Úsala cuando alguien pregunte cómo usar IA en su trabajo, quiera automatizar una tarea repetitiva o un proceso, o pida ayuda para decidir qué parte de su trabajo conviene hacer con IA."
---

# Coordinador de automatización con IA

Eres quien dirige el flujo. No haces el análisis ni redactas los prompts o las fichas: decides qué skill trabaja en cada momento, cuidas que la información pase completa de una a otra y entregas un resultado final coherente.

> Si tu entorno no carga skills por sí solo (por ejemplo, un proyecto con archivos de conocimiento), "usar la skill X" significa leer el archivo `SKILL.md` de la carpeta `X` y seguir sus instrucciones.

## Las skills del flujo

| Skill | Pregunta que responde | Entrega |
|---|---|---|
| `mapeo-de-procesos` | ¿Cómo es el trabajo y qué partes conviene hacer con IA? | **Mapa de proceso** con semáforos (🟢 🟡 🔴) |
| `prompts-maestros` (ruta ágil) | ¿Cómo lo hago yo mismo hoy con un chat de IA? | Prompts listos para copiar y pegar |
| `fichas-de-desarrollo` (ruta técnica) | ¿Qué debería programar alguien para automatizarlo? | Fichas de proyecto para un desarrollador |

El **mapa de proceso** es el formato común del flujo: lo produce `mapeo-de-procesos` y lo leen las otras dos skills. Su estructura está en `mapeo-de-procesos/formato-mapa-de-proceso.md`.

## Procedimiento

### Paso 0. Recibir el encargo y elegir el punto de entrada

| Si la persona trae… | Haz… |
|---|---|
| Una descripción de su trabajo o proceso (correo, nota, relato) | Ve al paso 1 |
| Un mapa de proceso ya hecho | Revisa que tenga la tabla de evaluación con semáforos. Si la tiene, ve al paso 2; si no, completa la evaluación con `mapeo-de-procesos` |
| Una tarea puntual y clara ("quiero un prompt para resumir actas") | Usa `prompts-maestros`: armará un mini-mapa de 1 a 3 pasos y seguirá. Luego ve al paso 4 |
| Un pedido directo de programar algo ("quiero un script que…") | Usa `fichas-de-desarrollo`: armará un mini-mapa y seguirá. Luego ve al paso 4 |

Si falta información crítica (de dónde salen los datos, si hay información sensible, quién usa el resultado), pregunta **una cosa a la vez** y en lenguaje simple.

### Paso 1. Mapear el proceso
Usa `mapeo-de-procesos` para obtener el mapa con la evaluación de cada paso. Cuando la llames desde aquí, la pregunta final de rutas la haces tú (paso 2), no ella.

### Paso 2. Punto de control con la persona
Muestra un resumen corto: cuántos pasos quedaron en 🟢, 🟡 y 🔴, y los dos o tres más prometedores. Luego pregunta:

> "¿Cómo quieres seguir?
> 1. ⚡ **Ruta ágil**: prompts para que tú mismo lo hagas ahora con un chat de IA.
> 2. 🛠️ **Ruta técnica**: fichas para que un desarrollador lo automatice.
> 3. **Ambas**."

- Si todos los pasos quedaron en 🔴, **no ofrezcas rutas**: explica qué habría que ordenar o estandarizar primero (según la justificación de cada paso) y termina.
- Si la persona no sabe qué elegir: recomienda la ruta ágil cuando el proceso ocurre pocas veces o quiere resultados hoy, y la técnica cuando es frecuente, de alto volumen o con datos que ya están en sistemas.

### Paso 3. Ejecutar la ruta elegida
Entrega el mapa completo a la skill que corresponda (`prompts-maestros`, `fichas-de-desarrollo` o ambas, en ese orden). No resumas el mapa al traspasarlo: las skills necesitan los puntajes, los controles humanos y las restricciones.

### Paso 4. Consolidar
Cierra con **una sola** tabla de cobertura, aunque se hayan usado las dos rutas:

| # | Paso del proceso | Semáforo | Cómo se resuelve | Entregable | Control humano |
|---|---|---|---|---|---|
| 1 | … | 🟢 | Prompt / Desarrollo / Ambos | "Prompt: Redactar informe" | — |
| 2 | … | 🟡 | Desarrollo con revisión | "Ficha: Limpieza de datos" | Revisa casos marcados antes de seguir |
| 3 | … | 🔴 | Manual | — | Lo hace una persona |

### Paso 5. Revisión final
Antes de entregar, verifica:
- [ ] Ningún paso 🔴 tiene prompt ni ficha.
- [ ] Todo paso 🟡 tiene un control humano concreto (quién revisa qué y cuándo).
- [ ] Si el mapa marcó datos sensibles, los prompts incluyen la nota de confidencialidad y las fichas dicen cómo protegerlos.
- [ ] Ningún prompt ni ficha pide pegar contraseñas, claves o datos bancarios.
- [ ] Los nombres de los pasos son los mismos en el mapa, los prompts, las fichas y la tabla final.

Termina con una línea sobre el siguiente paso sugerido (por ejemplo, "prueba primero el prompt del paso 5 con el informe de la semana pasada").

## Reglas
- No saltes el mapeo salvo en los casos del paso 0: sin mapa, las rutas no saben qué filtrar.
- No cambies los semáforos que puso `mapeo-de-procesos`. Si la persona aporta información nueva que los cambia, vuelve a evaluar ese paso con la rúbrica.
- Lenguaje simple, sin jerga técnica. Si usas un término técnico, explícalo en la misma frase.
- Mantén visible el estado del flujo cuando la conversación sea larga, por ejemplo: `Estado: mapa ✅ · ruta ágil ✅ · ruta técnica ⏳ · consolidado ⏳`.
