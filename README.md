# Claude Plugins

Colección curada de Skills, Agentes e instrucciones de proyecto (`CLAUDE.md`) para [Claude Code](https://claude.com/claude-code), recopilada y verificada (seguridad, confiabilidad y usabilidad) principalmente desde el catálogo de [aitmpl.com](https://www.aitmpl.com/).

## Estructura

Cada carpeta de nivel superior está lista para instalar directamente, en el formato exacto que espera Claude Code:

- **`skills/<nombre>/SKILL.md`** — 32 Skills. Cada carpeta se llama igual que el `name:` del frontmatter (minúsculas y guiones). La mayoría es un único `SKILL.md`; algunas (`scrollcraft`) traen además recursos propios (`scripts/`, `references/`, `engine/`, `templates/`) que se copian junto con la carpeta.
- **`agents/<nombre>.md`** — 14 definiciones de subagentes, un archivo suelto por agente.
- **`CLAUDE.md/<nombre>/CLAUDE.md`** — 3 instrucciones de proyecto/agente, cada una pensada para copiarse como `CLAUDE.md` en la raíz de un proyecto puntual (no se instalan en batch como las skills/agentes).

## Instalación

- **Global** (todos tus proyectos): copiá el contenido de `skills/` a `~/.claude/skills/` y el de `agents/` a `~/.claude/agents/`.
- **Por proyecto**: copiá solo las skills/agentes que apliquen a `<proyecto>/.claude/skills/` y `<proyecto>/.claude/agents/`.
- **CLAUDE.md**: copiá el archivo de `CLAUDE.md/<nombre>/CLAUDE.md` que corresponda a la raíz del proyecto donde querés que aplique.

## Nota

Los ítems fueron revisados manualmente para descartar contenido de baja calidad (plantillas genéricas sin sustancia), rutas o datos hardcodeados de otros usuarios, e instrucciones que intenten forzar el comportamiento del asistente. No incluye MCPs, hooks, comandos ni settings, ya que suelen depender de credenciales o configuración externa.
