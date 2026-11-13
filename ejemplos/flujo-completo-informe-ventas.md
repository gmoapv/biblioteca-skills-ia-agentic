# Ejemplo de flujo completo: informe de ventas

Muestra cómo `coordinador-automatizacion-ia` lleva un encargo desde el relato hasta el resultado consolidado, usando las dos rutas. El mapa completo de este caso está en [mapeo-de-procesos/ejemplos.md](../mapeo-de-procesos/ejemplos.md) (ejemplo 1).

## Paso 0. Encargo
> "Cada dos días reviso la base de ventas, limpio los datos, calculo indicadores, escribo un informe, lo paso a PDF y se lo mando a gerencia. Me toma toda la mañana. ¿Puedo usar IA?"

La persona trae una descripción de su trabajo → el coordinador parte por el mapeo.

## Paso 1. Mapa (resumen)
`mapeo-de-procesos` entrega 8 pasos: **6 🟢, 2 🟡 y ningún 🔴**.
- 🟡 Paso 3 (limpiar datos): la analista revisa las filas marcadas.
- 🟡 Paso 8 (enviar a gerencia): la analista aprueba el correo.

## Paso 2. Punto de control
> "Seis de tus ocho pasos se pueden hacer con IA o automatizar, y dos necesitan tu revisión. ¿Cómo quieres seguir? 1) Ruta ágil, 2) Ruta técnica, 3) Ambas."

La persona responde: **"Ambas: quiero algo para mañana y después pedirle a TI que lo automatice."**

## Paso 3a. Ruta ágil (extracto de `prompts-maestros`)

### ⚡ Prompt: Redactar el informe
**Para qué sirve**: convertir la tabla de indicadores en un informe breve para gerencia.
**Dónde usarlo**: cualquier chat de IA.

```markdown
Actúa como analista comercial que escribe para gerencia.
Tu objetivo es: redactar un informe breve de ventas del período a partir de la tabla de indicadores.

CONTEXTO Y DATOS:
"""
[PEGA AQUÍ LA TABLA DE INDICADORES DEL PERÍODO]
"""

INSTRUCCIONES:
1. Empieza con los tres hallazgos más importantes, en una línea cada uno.
2. Si algún indicador cae más de 10 %, ponlo primero y explica la diferencia con el período anterior.
3. Cierra con una sección "A vigilar" de máximo tres viñetas.
4. Si encuentras datos incompletos o inconsistentes, avísame en una lista aparte.

FORMATO DE RESPUESTA:
Texto de máximo una página, con títulos cortos y viñetas.

RESTRICCIONES:
- Usa solo las cifras de la tabla.
- No inventes datos. Si falta información, dilo.
```

**🔒 Nota de seguridad**: no pegues contraseñas, claves ni datos bancarios.

(Se generan también los prompts de los pasos 3, 6 y 8.)

## Paso 3b. Ruta técnica (extracto de `fichas-de-desarrollo`)

### 🚀 Proyecto: Informe de ventas automático
**Pasos del mapa que cubre**: 1, 2, 4 y 7 (🟢) y 8 (🟡).

1. **Objetivo técnico**: programa que consulta la base, calcula los indicadores, genera el PDF y deja el correo listo para aprobar.
2. **Herramientas sugeridas**: Python (`pandas` para datos y una librería de PDF), tarea programada cada dos días, correo de la organización.
3. **Qué debe tener listo la persona**: acceso de solo lectura a la base, definición escrita de cada indicador y tres informes anteriores como referencia.
4. **Plan de implementación**: preparar la conexión a la base → filtrar el período → calcular indicadores con las fórmulas definidas → detenerse y avisar si más del 5 % de los registros tiene campos vacíos → generar el PDF → crear el borrador del correo → probar con los datos de las últimas dos semanas.
5. **Controles humanos**: el correo queda como borrador; la analista lo revisa y lo envía (paso 8).
6. **Seguridad de los datos**: la clave de la base va en una variable de entorno, no en el código.

## Paso 4. Tabla consolidada

| # | Paso | Semáforo | Cómo se resuelve | Entregable | Control humano |
|---|---|---|---|---|---|
| 1 | Consultar la base de ventas | 🟢 | Desarrollo | Ficha: Informe de ventas automático | — |
| 2 | Extraer los datos del período | 🟢 | Desarrollo | Ficha: Informe de ventas automático | — |
| 3 | Limpiar y normalizar los datos | 🟡 | Prompt (por ahora) | Prompt: Limpiar y normalizar | Revisar filas marcadas antes del paso 4 |
| 4 | Calcular los indicadores | 🟢 | Desarrollo | Ficha: Informe de ventas automático | — |
| 5 | Redactar el informe | 🟢 | Prompt | Prompt: Redactar el informe | — |
| 6 | Revisar la consistencia | 🟢 | Prompt | Prompt: Revisar la consistencia | — |
| 7 | Exportar a PDF | 🟢 | Desarrollo | Ficha: Informe de ventas automático | — |
| 8 | Enviar a gerencia | 🟡 | Ambos | Prompt + ficha | La analista aprueba el correo |

## Paso 5. Revisión final
- ✅ Ningún paso 🔴 tiene prompt ni ficha (no hay 🔴).
- ✅ Los dos pasos 🟡 tienen control humano.
- ✅ No hay datos sensibles; los prompts llevan la nota de seguridad.
- ✅ Los nombres de los pasos coinciden en el mapa, los prompts, la ficha y la tabla.

**Siguiente paso sugerido**: prueba mañana el prompt "Redactar el informe" con la tabla del último período y compara el resultado con tu informe anterior.
