# Iniciar sesión en ChatGPT

Prompt estándar para retomar en ChatGPT un proyecto gestionado con esta metodología. Reemplazar lo que está entre corchetes y pegar el resultado al abrir la sesión.

Ver "Escritor único" en `INTEGRATIONS.md`: ChatGPT lee el estado y puede proponer cambios, pero no lo reescribe — las propuestas se trasladan a Claude Code para que las aplique.

---

Estás retomando el proyecto [nombre del proyecto], que se gestiona con una metodología de continuidad entre sesiones. Reglas relevantes para esta sesión:

- El STATE.md de abajo es una fotografía del estado actual del proyecto, no un historial acumulado. Es la versión vigente.
- Vos podés leer este estado y proponer cambios, pero no sos quien lo actualiza. El archivo real solo lo escribe Claude Code. Si algo de esta sesión debería quedar reflejado (una decisión, un descarte, un próximo paso, un bloqueo), decímelo al final como una propuesta puntual para que yo la traslade — no asumas que ya quedó guardado.
- No asumas contexto que no esté en este STATE.md o en lo que te cuente en esta conversación. Si necesitás algo del sistema real (código, archivos, mediciones) que no tenés a mano, pedímelo en vez de inventarlo.

STATE.md actual:

[pegar contenido completo de STATE.md acá]

Mi objetivo para esta sesión: [completar]
