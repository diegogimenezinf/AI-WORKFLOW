# AI-WORKFLOW

Metodología personal y agnóstica de herramienta para trabajar proyectos con IA (Claude, ChatGPT u otras), especialmente proyectos de varias sesiones. No define cómo debe estructurarse cada proyecto — define cómo decidir y gestionar el trabajo entre sesiones.

## Las dos reglas que gobiernan todo lo demás

1. **La metodología administra el contexto, no lo acumula.**
2. **El proyecto determina cuánto proceso necesita; la metodología no le impone estructura.**

Si algo en este repo contradice alguna de estas dos reglas, la regla gana.

## Capas

```
ENGANCHE            → cómo una sesión nueva se entera de que esta metodología existe
   ↓                   (CLAUDE.md global / prompt estándar en ChatGPT). Nada más vive acá.
METODOLOGÍA          → este repo: principios, prácticas, playbooks, integraciones
   ↓
PROYECTO             → CLAUDE.md del proyecto + STATE.md (viven EN el proyecto, no acá)
   ↓
SESIÓN                → objetivo de trabajo actual
   ↓
CHECKPOINT             → actualización del STATE.md al cierre, solo si cambió algo relevante
```

El enganche está limitado a apuntar hacia esta metodología. No es el lugar para definir tono, personalidad o autonomía general de la IA — eso es un problema distinto.

## Principios

1. **Derivable vs. no derivable** — No persistir información que ya es recuperable inspeccionando el sistema real (código, git log, mediciones, configuración). Persistir solo lo que se perdería si no quedara escrito: decisiones y su razón, alternativas descartadas, próximo paso, bloqueos.
2. **Estado ≠ historial** — El estado de un proyecto es una fotografía de cómo está ahora, no un registro de todo lo que pasó. Se sobrescribe, no se acumula. El historial completo, si hace falta, está en `git log` — no se duplica en el estado.
3. **Sesiones por objetivo, con umbral mínimo** — Una sesión representa un objetivo, no una cantidad de tiempo. Si una tarea se resuelve en una sesión y no se va a retomar, no se crea ningún artefacto de estado. La continuidad entre sesiones solo se gestiona cuando hay continuidad real que gestionar.
4. **Fuente de verdad** — Antes de asumir algo, comprobar el sistema real (código, git, mediciones, síntomas, manuales, pruebas). La memoria o el estado guardado no reemplazan esa comprobación.
5. **Verificación** — Un trabajo no se considera terminado porque la IA produjo una respuesta o modificó algo, sino porque existe una comprobación apropiada al tipo de tarea (test, build, medición, revisión).
6. **Clasificación Principio / Práctica / Playbook** — Principio: regla de decisión estable, casi nunca cambia. Práctica: un "cómo" mecánico aplicable a casi cualquier proyecto sin importar el dominio. Playbook: conocimiento específico de un dominio que solo algunos proyectos necesitan. Algo nuevo se agrega en el nivel que le corresponde según esta prueba, no en el que sea más cómodo escribir.
7. **Poda como mecanismo de evolución** — Las reglas y prácticas se agregan por fricción real, no por anticipación, y se eliminan cuando dejan de aportar. Esta poda se aplica también a este propio repositorio, no solo al estado de los proyectos — se revisa periódicamente si algo acá dejó de ganarse su lugar.
8. **Playbooks opcionales, nunca gates** — Un playbook es material de consulta para decidir mejor, nunca un checklist obligatorio ni una plantilla que un proyecto tiene que completar. Si un playbook empieza a tratarse como obligatorio, dejó de cumplir su función.

## Contenido del repo

- `PRACTICES.md` — cómo se gestionan en la práctica el contexto, las sesiones, el estado, la verificación y la evolución.
- `PLAYBOOKS/` — conocimiento específico por dominio (software, hardware, investigación...). Vacío hasta que un playbook concreto se necesite.
- `PROMPTS/` — prompts reutilizables. Por ahora: `INICIAR_CHATGPT.md`, el que retoma un proyecto en ChatGPT pegando su STATE.md.
- `INTEGRATIONS.md` — cómo se engancha esta metodología en Claude Code y en ChatGPT.

## Cómo se usa en un proyecto

Un proyecto que va a durar más de una sesión mantiene, en su propia carpeta (no acá):
- Sus instrucciones específicas (stack, convenciones, comandos).
- Un `STATE.md` corto: objetivo, decisiones clave y por qué, descartado y por qué, próximo paso, bloqueos, trampas conocidas.

Ver `PRACTICES.md` para el detalle de cuándo y cómo se actualiza.
