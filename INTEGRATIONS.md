# Integraciones

Cómo se engancha esta metodología según la herramienta. El contenido (principios, prácticas, playbooks) es el mismo — lo que cambia es el mecanismo de carga.

## Claude Code

- El CLAUDE.md global (`~/.claude/CLAUDE.md`) referencia este repositorio, para que cualquier sesión nueva sepa que existe.
- Cada proyecto mantiene su propio `CLAUDE.md` con sus instrucciones específicas, y referencia la ruta a su propio `STATE.md`.
- Los playbooks se pueden usar como Skills (`.claude/skills/`) cuando un proyecto necesita conocimiento de dominio bajo demanda, en vez de cargarlo siempre.
- Los subagentes son útiles para investigación pesada que no debería consumir el contexto principal de la sesión.
- Es el único que escribe `STATE.md` (ver "Escritor único" más abajo).

## ChatGPT

- No hay carga automática de archivos locales. La continuidad depende de pegar el contenido de `STATE.md` al empezar una sesión relacionada.
- Usar el prompt estándar de `PROMPTS/INICIAR_CHATGPT.md` para esto.
- Si se usa la función "Projects" de ChatGPT, sus instrucciones pueden pedir explícitamente el STATE.md actualizado al inicio si no se proveyó.
- ChatGPT solo lee `STATE.md`: no mantiene su propia versión ni lo reescribe. Si algo de la sesión debería quedar reflejado en el estado, se traslada a Claude Code para que lo aplique ahí.

## Escritor único

`STATE.md` tiene un solo escritor: Claude Code. Cualquier otra herramienta (ChatGPT u otra) puede leerlo y proponer cambios, pero nunca reescribirlo por su cuenta. Esto evita que existan dos versiones divergentes del estado de un proyecto.
