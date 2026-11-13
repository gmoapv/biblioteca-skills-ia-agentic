# 🤖 Biblioteca de skills para llevar la IA a tu trabajo

Cuatro **skills** (habilidades de agente) en español para descubrir qué partes de un trabajo conviene hacer con inteligencia artificial y dejarlas listas para usar: como prompts que la propia persona copia y pega, o como fichas para que un desarrollador las automatice.

No son prompts sueltos: son módulos de instrucciones que se encadenan. Funcionan en Claude (Claude Code, la app y Proyectos), ChatGPT, Gemini, Copilot y agentes como Antigravity, Cursor o Windsurf.

## 🔗 Cómo funciona el flujo

```
                 coordinador-automatizacion-ia
                 (recibe, enruta, consolida y revisa)
                              │
                              ▼
                     mapeo-de-procesos
          relato del trabajo → mapa con semáforos 🟢 🟡 🔴
                              │
              ┌───────────────┴───────────────┐
              ▼                               ▼
      prompts-maestros                fichas-de-desarrollo
       (ruta ágil)                       (ruta técnica)
  prompts para hacerlo hoy       fichas para que un desarrollador
     con un chat de IA                 lo automatice
```

| Skill | Para qué sirve | Recibe | Entrega |
|---|---|---|---|
| [`coordinador-automatizacion-ia`](./coordinador-automatizacion-ia/SKILL.md) | Dirige el flujo: decide por dónde partir, ofrece las rutas, une los resultados y hace una revisión final | El encargo de la persona | Tabla consolidada y revisión |
| [`mapeo-de-procesos`](./mapeo-de-procesos/SKILL.md) | Ordena el trabajo en pasos y decisiones, y puntúa cada paso con una rúbrica de 0 a 20 | Un relato (correo, nota, texto) | **Mapa de proceso** |
| [`prompts-maestros`](./prompts-maestros/SKILL.md) | Ruta ágil: prompts listos para copiar y pegar | Mapa de proceso | Tarjetas de prompts + tabla de cobertura |
| [`fichas-de-desarrollo`](./fichas-de-desarrollo/SKILL.md) | Ruta técnica: plan para construir la automatización | Mapa de proceso | Fichas de proyecto + matriz de alcance |

Las skills se pasan la información con un formato común, el **mapa de proceso** ([formato](./mapeo-de-procesos/formato-mapa-de-proceso.md)). Cada paso se evalúa con la [rúbrica de idoneidad para IA](./mapeo-de-procesos/rubrica-idoneidad-ia.md):

| Puntaje | Semáforo | Significa |
|---|---|---|
| 15–20 | 🟢 | Recomendable |
| 9–14 | 🟡 | Recomendable con control humano |
| 0–8 | 🔴 | No por ahora |

Puedes ver un caso de punta a punta en [ejemplos/flujo-completo-informe-ventas.md](./ejemplos/flujo-completo-informe-ventas.md).

## 📦 Instalación

**Claude Code**: copia las cuatro carpetas en `.claude/skills/` de tu proyecto, o en `~/.claude/skills/` para tenerlas en todos tus proyectos.

```bash
git clone https://github.com/gmoapv/biblioteca-skills-ia-agentic.git
cd biblioteca-skills-ia-agentic
mkdir -p ~/.claude/skills
cp -R coordinador-automatizacion-ia mapeo-de-procesos prompts-maestros fichas-de-desarrollo ~/.claude/skills/
```

**Claude (app o web)**: comprime cada carpeta en un .zip y súbelo en *Configuración → Capacidades → Skills*.

```bash
for s in coordinador-automatizacion-ia mapeo-de-procesos prompts-maestros fichas-de-desarrollo; do zip -qr "$s.zip" "$s" -x '*.DS_Store'; done
```

**Proyectos de Claude o GPT personalizados**: sube los archivos `.md` de las cuatro carpetas como conocimiento y agrega en las instrucciones:
> "Tienes cuatro skills en tu conocimiento. Cuando alguien quiera usar IA en su trabajo, sigue `coordinador-automatizacion-ia/SKILL.md`, que te dirá cuándo usar las otras tres."

**Antigravity, Cursor, Windsurf u otros agentes**: copia las carpetas en tu espacio de trabajo e invócalas por su nombre (por ejemplo, *"usa @coordinador-automatizacion-ia para analizar esto"*).

**Uso manual**: pega el contenido de `coordinador-automatizacion-ia/SKILL.md` como primer mensaje de una conversación y luego el de cada skill cuando el coordinador la pida.

## 💬 Cómo usarlo
Cuenta tu trabajo con tus palabras, por ejemplo:
> "Todos los lunes junto los reportes de las sucursales, los reviso y hago un resumen para la jefatura. ¿Qué parte podría hacer con IA?"

El coordinador te devuelve el mapa, te pregunta qué ruta prefieres y cierra con una tabla de qué se resuelve con prompts, qué con desarrollo y qué sigue siendo manual.

## 🔄 Cambio de nombres (versión 2)
| Antes | Ahora |
|---|---|
| — | `coordinador-automatizacion-ia` (nueva) |
| `Work_Interpreter` | `mapeo-de-procesos` |
| `Prompt_Assistant` | `prompts-maestros` |
| `Proposal_Generator` | `fichas-de-desarrollo` |

Si invocabas las skills por su nombre antiguo (por ejemplo, `@Work_Interpreter`), usa el nuevo. El detalle de los cambios está en [CHANGELOG.md](./CHANGELOG.md).

## 📂 Estructura del repositorio
```
coordinador-automatizacion-ia/   SKILL.md
mapeo-de-procesos/               SKILL.md, formato-mapa-de-proceso.md, rubrica-idoneidad-ia.md, ejemplos.md
prompts-maestros/                SKILL.md
fichas-de-desarrollo/            SKILL.md
ejemplos/                        flujo completo de punta a punta
```
