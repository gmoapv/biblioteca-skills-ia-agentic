# Formato del mapa de proceso

Es el formato común del flujo. Lo produce `mapeo-de-procesos` y lo leen `prompts-maestros`, `fichas-de-desarrollo` y `coordinador-automatizacion-ia`. Usa siempre estos títulos y columnas, en este orden, para que las otras skills encuentren la información.

## Plantilla

```markdown
## Mapa de proceso: [nombre corto del proceso]

### 1. Ficha del proceso
- **Objetivo**: …
- **Frecuencia**: diaria / semanal / mensual / "cada vez que …"
- **Responsables**: …
- **Insumos**: … (correos, planillas, PDF, sistema X)
- **Salidas**: … (informe, correo, registro)
- **Restricciones**: … (plazos, herramientas permitidas)
- **Datos sensibles**: Sí / No — [cuáles: datos personales, salud, finanzas, legales]

### 2. Pasos
| # | Paso | Responsable | Insumo | Salida |
|---|---|---|---|---|
| 1 | Verbo + objeto ("Descargar la base de ventas") | … | … | … |

### 3. Puntos de decisión
- Después del paso N: si [condición] → [qué se hace].

### 4. Evaluación de idoneidad para IA
| # | Paso | T | E | R | D | Puntaje | Etiqueta | Semáforo | Tipo de uso | Justificación y control humano |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | … | 5 | 5 | 4 | 5 | 19 | SÍ | 🟢 | Automatización tradicional | … |

### 5. Hoja de ruta por fases
- **Fase 1 – Logros rápidos**: …
- **Fase 2 – Menos errores**: …
- **Fase 3 – Automatización**: …
```

T, E, R y D son las cuatro dimensiones de la rúbrica (ver `rubrica-idoneidad-ia.md`).

## Valores permitidos
- **Etiqueta**: `SÍ`, `CONDICIONADA`, `NO`.
- **Semáforo**: 🟢 (recomendable), 🟡 (recomendable con control humano), 🔴 (no por ahora).
- **Tipo de uso**: `Asistente` (la IA hace un borrador y la persona lo usa), `Control de calidad` (la IA revisa o detecta errores), `Automatización parcial` (la máquina hace el trabajo y una persona aprueba), `Automatización tradicional` (reglas fijas o programas, sin IA generativa), `Apoyo a la decisión` (la IA ordena información y decide una persona).

## Bloque JSON opcional
Agrégalo al final cuando el mapa vaya a pasar a un desarrollador o a otra herramienta:

```json
{
  "proceso": "Informe de ventas",
  "frecuencia": "cada dos días",
  "datos_sensibles": false,
  "pasos": [
    {"id": 1, "paso": "Consultar la base de ventas", "t": 5, "e": 5, "r": 4, "d": 5,
     "puntaje": 19, "etiqueta": "SÍ", "semaforo": "verde",
     "tipo_uso": "Automatización tradicional", "control_humano": ""}
  ],
  "decisiones": [{"despues_de": 3, "condicion": "faltan datos", "accion": "avisar al responsable"}]
}
```

`semaforo` usa las palabras `verde`, `amarillo` o `rojo`.

## Mapas que no siguen este formato
Si llega un mapa antiguo o hecho a mano (por ejemplo, con el título "Análisis de Oportunidad IA"), toma los pasos y semáforos que encuentres. Si un paso no tiene semáforo o puntaje, evalúalo con la rúbrica antes de usarlo.
