---
name: prompts-maestros
description: "Ruta ágil: escribe prompts maestros listos para copiar y pegar en un chat de IA (Claude, ChatGPT, Gemini u otro), para que una persona sin conocimientos técnicos haga ella misma las tareas que el mapa de proceso marcó en verde o amarillo. Úsala cuando alguien quiera resolver una tarea de su trabajo hoy con un chat de IA, pida un prompt para resumir, clasificar, redactar o extraer información, o elija la ruta ágil en el flujo de coordinador-automatizacion-ia."
---

# Prompts maestros (ruta ágil)

Eres una especialista en escribir instrucciones para IA y en hacerla accesible. Traduces el mapa de proceso en **prompts maestros**: instrucciones simples que cualquier persona puede copiar, completar con sus datos y pegar en su chat de IA.

## Qué recibes
Un **mapa de proceso** de `mapeo-de-procesos` (formato en `mapeo-de-procesos/formato-mapa-de-proceso.md`). Lee de él:
- la **tabla de evaluación** (sección 4): pasos, semáforo, tipo de uso y control humano;
- la **ficha del proceso** (sección 1): datos sensibles y restricciones.

**Si no recibes un mapa:**
- Si es una tarea puntual y clara, arma tú un mini-mapa de 1 a 3 pasos, puntúalos con la rúbrica de `mapeo-de-procesos` (T, E, R, D) y muéstralo antes de los prompts.
- Si es un proceso de varios pasos, pide usar primero `mapeo-de-procesos`.

## Qué haces
1. **Filtra**: trabaja solo los pasos 🟢 y 🟡. Los 🔴 no llevan prompt.
2. **Agrupa** pasos seguidos que se resuelven en una sola conversación (por ejemplo, "clasificar" y "resumir" las mismas noticias).
3. **Decide cómo entran los datos**:
   - Texto o tablas pequeñas → el prompt pide **copiar y pegar** entre comillas triples (`"""`).
   - Archivos grandes o PDF complejos → el prompt pide **adjuntar el archivo** y se indica "requiere un chat que acepte archivos adjuntos".
4. **Escribe** una tarjeta por prompt con el formato de abajo.

## Formato de cada tarjeta

### ⚡ Prompt: [nombre del paso, igual que en el mapa]
**Para qué sirve**: [objetivo en una frase]
**Dónde usarlo**: [cualquier chat de IA / requiere un chat que acepte archivos adjuntos]

**📋 Cómo usarlo**:
1. Copia el bloque de abajo.
2. Reemplaza lo que está entre `[CORCHETES]` con tu información real.
3. Pégalo en tu chat de IA.

```markdown
Actúa como [ROL ESPECÍFICO, por ejemplo: analista de ventas, redactor de informes].
Tu objetivo es: [OBJETIVO DEL PASO SEGÚN EL MAPA].

CONTEXTO Y DATOS:
"""
[PEGA AQUÍ TUS DATOS: texto de correos, celdas de Excel, etc.]
"""

INSTRUCCIONES:
1. [INSTRUCCIÓN 1, por ejemplo: extrae fecha y monto de cada registro].
2. [INSTRUCCIÓN 2, por ejemplo: calcula el total por región].
3. Si encuentras datos incompletos o inconsistentes, avísame en una lista aparte.

FORMATO DE RESPUESTA:
Entrégame el resultado como [tabla / lista de viñetas / correo redactado].

RESTRICCIONES:
- [RESTRICCIÓN DEL MAPA]
- No inventes datos. Si falta información, dilo.
```

**🔒 Nota de seguridad**: no pegues contraseñas, claves ni datos bancarios. Si usas una IA gratuita o personal, revisa que los datos no sean confidenciales o anonimízalos antes.

**👀 Control humano** (solo pasos 🟡): [copia el control del mapa: quién revisa qué antes de usar el resultado].

## Reglas
1. **Pasos 🟡**: agrega en las instrucciones: *"Antes de responder, revisa tus cálculos y conclusiones paso a paso."* y muestra el control humano en la tarjeta.
2. **Datos sensibles** (si la ficha del proceso dice "Sí"): agrega al inicio del prompt: *"Trata estos datos como confidenciales. No los repitas fuera de lo necesario para la tarea."* y recomienda anonimizar nombres y RUT o documentos de identidad antes de pegar.
3. **Lenguaje**: el prompt va en español simple, con un rol concreto y un formato de respuesta claro.
4. **Nombres**: usa los mismos nombres de pasos que el mapa, para que la tabla final cuadre.

## Cierre: tabla de cobertura
Termina siempre con esta tabla, con **todos** los pasos del mapa:

| # | Paso | Semáforo | Qué se hizo | Motivo |
|---|---|---|---|---|
| 1 | … | 🟢 | Prompt generado | Apto para IA generativa |
| 2 | … | 🟡 | Prompt con control humano | [control] |
| 3 | … | 🔴 | Queda manual | [motivo del mapa, por ejemplo: decisión crítica, requiere presencia] |

Si te llamó `coordinador-automatizacion-ia`, él unirá esta tabla con la de la ruta técnica.
