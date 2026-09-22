# Prácticas

Cómo se aplican los principios de `README.md` en el día a día. Si una práctica de acá contradice un principio, el principio gana.

## Gestión de contexto

Al empezar una sesión, reconstruir contexto en este orden, sin releer conversaciones pasadas:

1. Instrucciones del proyecto (CLAUDE.md o equivalente).
2. `STATE.md` del proyecto (corto, vigente).
3. Si algo no es obvio, inspeccionar el sistema real (código, `git log`, estructura de archivos) antes de asumir o preguntar.
4. Solo si hace falta profundidad histórica, consultar `git log` puntualmente — no por defecto.

Durante la sesión, la conversación es contexto de trabajo temporal. No todo lo hablado merece pasar al estado persistente (Principio 1).

## Gestión de sesión

Una sesión = un objetivo. Cuando el objetivo cambia a algo no relacionado, cerrar o limpiar contexto en vez de seguir acumulando.

Flujo adaptable — no son fases obligatorias, son pasos que se activan según haga falta:

```
ENTENDER
   ↓
¿Necesita planificación? ──NO──→ EJECUTAR
   │ SÍ                              ↑
   ↓                                 │
PLANIFICAR ─────────────────────────→┘
                                      ↓
                                  VERIFICAR
                                      ↓
                         ¿Terminó? ─NO─→ (volver a EJECUTAR)
                              │ SÍ
                              ↓
          ¿Cambió algo relevante para continuar? ─NO─→ fin, sin tocar STATE.md
                              │ SÍ
                              ↓
                    ACTUALIZAR STATE.md (checkpoint)
```

Planificar tiene sentido cuando el alcance es ambiguo, toca varios archivos/sistemas, o el enfoque no es obvio. Si el cambio se puede describir en una frase, se salta directo a ejecutar.

**Umbral mínimo (Principio 3):** si no hay continuidad esperada, no se crea `STATE.md` ni ningún otro artefacto. La sesión termina y ya.

## Gestión de estado (STATE.md)

Formato:

```
Objetivo: [una línea]

Decisiones clave:
- [decisión] — porque [razón no obvia desde el código/sistema]

Descartado:
- [alternativa] — porque [razón]

Próximo paso: [acción concreta]

Bloqueos / preguntas abiertas:
- [si hay]

Trampas conocidas:
- [intentos que no funcionaron y por qué, si aplica]
```

Reglas:

- Se sobrescribe. Cuando una decisión deja de ser relevante (se revirtió, quedó obsoleta), se borra del archivo — no se archiva ahí.
- Se actualiza solo si algo cambió que la próxima sesión necesitaría saber (próximo paso, una decisión nueva, un bloqueo). Si nada de eso cambió, no se toca.
- Si el archivo supera ~1-2 pantallas, es señal de que se está usando como bitácora en vez de como estado — podarlo.
- El razonamiento de decisiones que ya no están vigentes pero podrían hacer falta algún día no vive en `STATE.md` — vive en los mensajes de commit de git.

## Verificación

Nada se da por terminado sin una comprobación objetiva apropiada al tipo de trabajo:

- Software: tests, build, linter, comparación visual contra un diseño.
- Hardware: una medición, una prueba repetible, un síntoma que desaparece.
- Investigación: una fuente verificable, un cálculo que cierra.

Si no hay forma de verificar, decirlo explícitamente en vez de asumir que "quedó bien".

## Evolución

- Una práctica o principio se agrega cuando un problema se repite, no por anticipación.
- Una regla que ya no aporta se elimina, no se deja "por las dudas".
- El "por qué" de un cambio va en el mensaje de commit al modificar este repo — no hace falta un changelog aparte, para eso está `git log`.
- Esta poda se aplica también a este repositorio: si `PRACTICES.md` o `README.md` empiezan a acumular contenido que ya no se usa, se recorta.
