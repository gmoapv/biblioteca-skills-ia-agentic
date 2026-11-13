# Ejemplos de mapeo de procesos

Dos mapas completos con el [formato común](formato-mapa-de-proceso.md) y la [rúbrica](rubrica-idoneidad-ia.md). Los puntajes son ilustrativos: cambian según el contexto real de cada persona.

---

## Ejemplo 1: informe de ventas

**Relato de la persona**: "Cada dos días reviso la base de datos de ventas, saco los datos del período, los limpio, calculo los indicadores, escribo un informe con lo más importante, lo reviso, lo paso a PDF y se lo mando a gerencia."

## Mapa de proceso: Informe de ventas

### 1. Ficha del proceso
- **Objetivo**: informar a gerencia cómo van las ventas del período.
- **Frecuencia**: cada dos días.
- **Responsables**: analista comercial.
- **Insumos**: base de datos de ventas.
- **Salidas**: informe en PDF enviado por correo.
- **Restricciones**: debe estar listo antes de las 10:00.
- **Datos sensibles**: No (cifras agregadas, sin datos de clientes).

### 2. Pasos
| # | Paso | Responsable | Insumo | Salida |
|---|---|---|---|---|
| 1 | Consultar la base de ventas | Analista | Base de datos | Consulta abierta |
| 2 | Extraer los datos del período | Analista | Consulta | Planilla del período |
| 3 | Limpiar y normalizar los datos | Analista | Planilla | Planilla limpia |
| 4 | Calcular los indicadores | Analista | Planilla limpia | Tabla de indicadores |
| 5 | Redactar el informe | Analista | Indicadores | Borrador |
| 6 | Revisar la consistencia | Analista | Borrador | Informe revisado |
| 7 | Exportar a PDF | Analista | Informe | PDF |
| 8 | Enviar a gerencia | Analista | PDF | Correo enviado |

### 3. Puntos de decisión
- Después del paso 3: si más del 5 % de los registros tiene campos vacíos → avisar a quien administra la base antes de seguir.
- Después del paso 4: si un indicador cae más de 10 % → destacarlo al inicio del informe.

### 4. Evaluación de idoneidad para IA
| # | Paso | T | E | R | D | Puntaje | Etiqueta | Semáforo | Tipo de uso | Justificación y control humano |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Consultar la base de ventas | 5 | 5 | 4 | 5 | 19 | SÍ | 🟢 | Automatización tradicional | Consulta fija, siempre igual |
| 2 | Extraer los datos del período | 5 | 5 | 4 | 5 | 19 | SÍ | 🟢 | Automatización tradicional | Filtro por fechas |
| 3 | Limpiar y normalizar los datos | 3 | 3 | 3 | 5 | 14 | CONDICIONADA | 🟡 | Automatización parcial | Hay casos borde. Control: la analista revisa las filas marcadas antes del paso 4 |
| 4 | Calcular los indicadores | 5 | 4 | 3 | 5 | 17 | SÍ | 🟢 | Automatización tradicional | Fórmulas conocidas (si no estuvieran definidas, sería 🔴) |
| 5 | Redactar el informe | 5 | 4 | 3 | 5 | 17 | SÍ | 🟢 | Asistente | Tarea de lenguaje con insumo ordenado |
| 6 | Revisar la consistencia | 4 | 4 | 3 | 5 | 16 | SÍ | 🟢 | Control de calidad | La IA compara cifras del texto con la tabla |
| 7 | Exportar a PDF | 5 | 5 | 5 | 5 | 20 | SÍ | 🟢 | Automatización tradicional | Paso mecánico |
| 8 | Enviar a gerencia | 5 | 5 | 1 | 5 | 16 | CONDICIONADA | 🟡 | Automatización parcial | R = 1: cifras erróneas afectan decisiones. Control: la analista aprueba el borrador del correo |

### 5. Hoja de ruta por fases
- **Fase 1 – Logros rápidos**: usar un chat de IA para redactar (5) y revisar (6) el informe.
- **Fase 2 – Menos errores**: asistente de limpieza que marca filas dudosas (3).
- **Fase 3 – Automatización**: programa que consulta, extrae, calcula, exporta y deja el correo listo para aprobar (1, 2, 4, 7, 8).

---

## Ejemplo 2: monitoreo de noticias

**Relato de la persona**: "Todos los días reviso varios sitios de noticias, identifico los temas, clasifico las notas y mando un informe por correo al equipo."

## Mapa de proceso: Monitoreo diario de noticias

### 1. Ficha del proceso
- **Objetivo**: que el equipo conozca cada mañana las noticias relevantes para su área.
- **Frecuencia**: diaria.
- **Responsables**: encargada de comunicaciones.
- **Insumos**: lista de sitios de noticias.
- **Salidas**: informe diario por correo y registro histórico.
- **Restricciones**: no reproducir textos completos ni citas largas (derechos de autor).
- **Datos sensibles**: No.

### 2. Pasos
| # | Paso | Responsable | Insumo | Salida |
|---|---|---|---|---|
| 1 | Revisar la lista de fuentes | Encargada | Lista de sitios | Fuentes del día |
| 2 | Recopilar los artículos nuevos | Encargada | Sitios | Lista de artículos |
| 3 | Filtrar los irrelevantes | Encargada | Lista | Artículos relevantes |
| 4 | Clasificar por tema | Encargada | Artículos relevantes | Artículos por tema |
| 5 | Extraer las ideas clave | Encargada | Artículos por tema | Resúmenes breves |
| 6 | Redactar el informe diario | Encargada | Resúmenes | Borrador |
| 7 | Validar la selección final | Encargada | Borrador | Informe aprobado |
| 8 | Enviar por correo | Encargada | Informe aprobado | Correo enviado |
| 9 | Guardar el registro | Encargada | Informe | Archivo histórico |

### 3. Puntos de decisión
- Después del paso 3: si una noticia menciona directamente a la organización → marcarla como prioritaria.

### 4. Evaluación de idoneidad para IA
| # | Paso | T | E | R | D | Puntaje | Etiqueta | Semáforo | Tipo de uso | Justificación y control humano |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Revisar la lista de fuentes | 5 | 5 | 4 | 5 | 19 | SÍ | 🟢 | Automatización tradicional | Lista fija |
| 2 | Recopilar los artículos nuevos | 5 | 3 | 4 | 4 | 16 | SÍ | 🟢 | Automatización tradicional | Lectura de RSS o sitios; formatos variables |
| 3 | Filtrar los irrelevantes | 4 | 3 | 3 | 5 | 15 | SÍ | 🟢 | Asistente | Criterios de relevancia escribibles |
| 4 | Clasificar por tema | 5 | 3 | 4 | 5 | 17 | SÍ | 🟢 | Asistente | Tarea de lenguaje |
| 5 | Extraer las ideas clave | 5 | 3 | 3 | 5 | 16 | SÍ | 🟢 | Asistente | Resumir con palabras propias, sin citas largas |
| 6 | Redactar el informe diario | 5 | 4 | 3 | 5 | 17 | SÍ | 🟢 | Asistente | Insumo ya ordenado |
| 7 | Validar la selección final | 3 | 3 | 1 | 5 | 12 | CONDICIONADA | 🟡 | Apoyo a la decisión | R = 1: qué se informa es criterio editorial. Control: la encargada aprueba antes de enviar |
| 8 | Enviar por correo | 5 | 5 | 3 | 5 | 18 | SÍ | 🟢 | Automatización tradicional | Solo después del paso 7 |
| 9 | Guardar el registro | 5 | 5 | 5 | 5 | 20 | SÍ | 🟢 | Automatización tradicional | Paso mecánico |

### 5. Hoja de ruta por fases
- **Fase 1 – Logros rápidos**: prompt diario que filtra, clasifica, resume y redacta (3 a 6).
- **Fase 2 – Menos errores**: lista de criterios de relevancia escrita y revisada cada mes.
- **Fase 3 – Automatización**: programa que recopila, prepara el borrador, espera la aprobación (7), envía y archiva.
