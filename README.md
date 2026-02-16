# 🤖 Biblioteca de Skills de IA (Agentic Workflow)

Esta biblioteca contiene **Habilidades de Agente (Skills)** diseñadas para integrarse en flujos de trabajo avanzados de IA (como **Antigravity**, **Claude Projects**, **GitHub Copilot/Codex** o **Custom GPTs**).

No son simples "prompts" para copiar y pegar; son **módulos de instrucción estructurada** que dotan a la IA de capacidades específicas para ejecutar procesos complejos en cadena.

## � El Flujo de Trabajo (The Chain)

Estas skills están diseñadas para encadenarse secuencialmente:

1.  **[Work Interpreter](./Work_Interpreter/SKILL.md)** 🧠 (Análisis)
    *   **Input:** Descripción vaga de un requerimiento (email, nota de voz, texto).
    *   **Output:** Mapa de *Process Analysis* estructurado (JSON/Markdown) con semáforos de viabilidad.
    *   **Función:** Actúa como el "Arquitecto" que entiende qué se debe hacer antes de ejecutar.

2.  **[Prompt Assistant](./Prompt_Assistant/SKILL.md)** 🛠️ (Ingeniería)
    *   **Input:** El Mapa de *Process Analysis* del paso anterior.
    *   **Output:** "Prompt Maestro" optimizado y validado.
    *   **Función:** Transforma el "qué hacer" en instrucciones técnicas precisas para la IA ejecutora.

3.  **[Proposal Generator](./Proposal_Generator/SKILL.md)** 📄 (Ejecución)
    *   **Input:** Datos crudos + El "Prompt Maestro".
    *   **Output:** Documento final (Propuesta, Reporte, Correo) en formato profesional.
    *   **Función:** Ejecuta la tarea final con alta precisión.

---

## � Cómo Instalar / Usar

### Opción A: En Entornos de Agentes (Antigravity, Cursor, Windsurf)
Si usas un IDE o Agente con capacidad de leer contexto local:

1.  **Copia** las carpetas `Work_Interpreter`, `Prompt_Assistant` y `Proposal_Generator` dentro de tu proyecto o espacio de trabajo.
2.  **Invoca** la skill mencionándola en el chat con tu agente (ej: *"Usa la skill @Work_Interpreter para analizar esto..."*).
3.  El Agente leerá automáticamente el archivo `SKILL.md` para entender su rol y restricciones.

### Opción B: En Claude Projects / ChatGPT Team
Para crear un entorno de trabajo persistente:

1.  Crea un nuevo **Project** (Claude) o **Custom GPT**.
2.  Sube los archivos `SKILL.md` de cada carpeta a la sección de **Knowledge / Knowledge Base**.
3.  En las **Custom Instructions**, indica:
    > "Tienes acceso a 3 skills definidas en tu Knowledge: Work Interpreter, Prompt Assistant y Proposal Generator. Úsalas secuencialmente cuando se requiera procesar una solicitud compleja."

### Opción C: Uso Manual Avanzado
Puedes copiar el contenido de `SKILL.md` y pegarlo como un "System Prompt" inicial para configurar una sesión de chat larga.

---

## 📂 Estructura del Repositorio

*   `/Work_Interpreter`: Lógica de análisis y estructuración de procesos.
*   `/Prompt_Assistant`: Lógica de meta-prompting y optimización.
*   `/Proposal_Generator`: Plantillas y lógica de redacción final.
