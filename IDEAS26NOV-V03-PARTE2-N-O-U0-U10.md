# Ideas26nov v0.3 · Parte 2/3 · Observación, cuarentena y evolución por unidades

**Síntesis de investigación pública · 26 noviembre 2026.** Fuente: mensaje reenviado «Ideas26nov · PARTE 2 de 3», leído en la sesión de revisión del SWARM. Esta página **resume y adapta solo los contenidos presentes en esa Parte 2**; no es una transcripción del correo, ni una comisión, ni una autorización de despliegue. El documento conserva las categorías PROPOSED/KEEP/HOLD/DISCARD y distingue referencias externas de pruebas del SWARM. No revela correo, interlocutores, recibos privados, credenciales, dispositivos, sesiones o rutas de infraestructura.

**Continuidad:** [Parte 1 / StrongDM + P1–P7](CONTINUIDAD-AGENTIC-SWARM-2026-11-26.md) · [MVP de los doce dominios](MVP-NATIVO-SKILLS-12-DOMINIOS-2026-11-26.md). **Parte 3/3:** `NO_DATA(source_not_available)`; en ella se anuncia el texto completo de CAMALEÓN v0.3 y los cambios detallados de prompts. No anticiparlos como contratos aprobados.

## 0-bis · Reconciliación PRE-R6

La Parte 2 llega después de que el catálogo de **12 identidades de referencia** A–K + NEXO-09 y sus skills propuestas se publicara como estudio. No sustituye ninguna ficha; amplía el catálogo **documental** de capacidades.

| Dimensión | Estado declarado | Límite |
|---|---|---|
| R5, ciclo de trabajo | `CLOSED_ADMINISTRATIVELY_BY_SOVEREIGN` | No certifica aceptación ni firma criptográfica |
| R5, aceptación técnica | `HOLD` | FAIL reproducibles, SKIP y NO_DATA siguen visibles |
| R6 | `PLAN_ONLY` | No construcción automática |
| R7 | `NOT_ACTIVATED` | No inferir activación |
| N/O, contratos | `PROPOSED` con fuente disponible en esta Parte 2 | No procesos LIVE, no grants ni permisos delegados |
| Partes de Ideas26nov | 1/3 y 2/3 recuperadas | 3/3 pendiente |

## IV · N · VIGÍA y O · ADUANA

Se proponen como **dos responsabilidades documentales separables** para la investigación externa, no como trabajadores ya iniciados. Se puede empezar estudiando estas funciones dentro de las herramientas y titulares existentes; su eventual activación precisa otra decisión.

### N · VIGÍA — exploración de anchura

**Problema:** hallar piezas relevantes sin repetir búsqueda costosa ni confundir popularidad o metadatos con evidencia de confianza.

**MVP propuesto:** `REGISTRO-DE-VIGÍA` con ID determinista, tiers de observación, release/tag/commit, OWNER y LICENSE declarados, `source`, `observed_at` y `freshness_ttl`. GitHub/MCP **solo lectura**, cadencia del scheduler ya existente, cursor ligado a versión y scope y `complete` explícito.

**Skills documentales:** `n.repo_watchlist`, `n.sighting_receipt`, `n.pagination_integrity`, `n.provenance_signals`, `n.claim_vs_observed`.

**Pruebas:** transferencia de propietario, cambio de licencia entre páginas, typosquat, rate-limit y datos externos que intentan introducir instrucciones. Objetivo **0 falsos COMPLETE y 0 falsos LIVE**; sobrepresupuesto → `NO_DATA(budget_exceeded)`, no recorte silencioso. Un avistamiento solo se considera útil si O lo consume.

### O · ADUANA — evaluación profunda y cuarentena

**Problema:** evitar que una fuente exterior mal verificada se convierta en código, permisos o referencia aprobada dentro del sistema.

**MVP propuesto:** `FICHA DE PATRÓN` con **problema → fuente+licencia → componente existente → adaptación mínima → baseline/métrica → fixture adversarial → riesgo/rollback → KEEP/HOLD/DISCARD → próxima pieza**; procedencia por tiers `official → verified → community → fork-no-auditado`.

**Skills documentales:** `o.pattern_quarantine`, `o.license_gate`, `o.fork_divergence_audit`, `o.injection_probe`, `o.ficha_patron`.

**Pruebas:** README con prompt injection, instrucciones de ejecución externa no autorizada, license laundering, star-farming y divergencia de forks. Ningún código de terceros se ejecuta. Sin licencia exacta → `HOLD`. Una prueba que no inyectó realmente el fallo → `NO_DATA(injection_not_applied)`.

### Cadencia propuesta y flujo

**Tiers de watchlist:** T1 diario para proyectos de alto seguimiento; T2 semanal para especificaciones y herramientas; T3 bajo demanda. La Parte 2 nombra como candidatos T1 Hermes Agent, Orca, OpenCode, celld, Hermes self-evolution y Playwright MCP; T2 MCP Tasks, chrome-devtools y estudio defensivo de forks. La cadencia propuesta **no autoriza crear otro cron**.

```text
Soberano aprueba watchlist
    → coordinación existente
    → N · AVISTAMIENTO (lectura)
    → O · FICHA / CUARENTENA (dato no confiable)
    → NEXO · deduplicación repo + commit + patrón
    → C · grafo y procedencia
    → D · juicio independiente
    → Soberano · decisión sobre KEEP/HOLD/DISCARD
    → manifiesto de adaptación privada, si se autoriza
```

**Conteo del catálogo conceptual:** A–K (11) + NEXO (1) + capacidades L/M/P (3) + propuestas N/O (2) = **17 referencias**, no 17 agentes ejecutando. R es alias de J y no se cuenta otra vez. `F · VECTOR` y `F · Concurrencia` son nombres por reconciliar dentro del mismo dominio, no dos agentes.

## V · Deltas U0–U10 propuestos

Todas las unidades siguen `status=PROPOSED`; pueden investigarse independientemente, pero **ninguna se instala ni gana grants por aparecer aquí**.

| Unidad | Adaptación al sistema existente | Prueba falsable | Dependencia de diseño |
|---|---|---|---|
| **U0 · Atribución/política** | Iniciador comprobado por solicitud y evaluator en el MCP existente, no autoridad nueva | Principal desconocido o permiso no vigente → DENY | Manifiesto y decisión soberana |
| **U1 · Fencing del receptor** | Cola serializada y revisión monótona protegidas por mecanismo existente, inspirado en celld | Escritura vieja tras pausa/retorno nunca produce efecto | Tras U0; CAS y recurso efectivos |
| **U2 · Default-deny** | Rechazo por defecto de acciones con efecto, políticas por llamada, reutilización del gate | Sin grant, unknown o firma inválida → DENY | Tras U0 |
| **U3 · Skills anti-drift** | Ciclo `PROPOSED → review → pinned → locked`, con revisión antes de consolidar | Skill locked no se altera y mejora no revisada no se autopromueve | Tras U0 |
| **U4 · Coste/capacidad** | Enrutamiento evidence/drafting y coste por operación, separando Wh de estimaciones | Fuera de presupuesto → NO_DATA/denegación; coste sin instrumento no es 0 | U0 + baseline P4 |
| **U5 · Procedencia/cuarentena** | Tiers de fuente y puerta de LICENSE, reutilizar MANIFEST y juez | Inyección, fork dudoso o licencia no corroborada no atraviesan KEEP | Paralela a U0 |
| **U6 · Contratos N/O** | AVISTAMIENTO + FICHA + REGISTRO y matriz, sin nuevos servicios | Cambio owner/licencia/páginas y contenido hostil no causan falsos COMPLETE/KEEP | Tras U5 + watchlist aprobada |
| **U7 · MCP Tasks** | Manejar tareas largas mediante handle durable y polling/cancel en MCP existente | Expiración o revocación explícita, cancelación con efecto fenced, sin falso final | Tras U0/U1/U2 y revisión de compatibilidad |
| **U8 · Evolución de skills/prompts** | Trazas → candidato → tests/semántica/secret detection → PR y revisión humana | Locked inmutable; fuga de secreto y deriva semántica → FAIL | Tras U3/U4 |
| **U9 · UI determinista y aislamiento** | Snapshot accesible JSON, navegador aislado por actor, una pestaña por titular, permiso granular | Sin fuga de cookies entre contextos, sin falso estado, inyección DOM registrada | Tras U5 y licencias verificadas |
| **U10 · CAMALEÓN v0.3 + MD** | Reconciliar ARRANQUE/RECOVER, encabezados versionados, rollback digest y presencia en `main` | No herencia de turnos CLI, ningún prompt se autoaplica, hash en destino exacto | **Parte 3/3 no disponible** + baseline + aprobación |

La fuente enfatiza para U7 algunos requisitos específicos a contrastar contra la especificación MCP Tasks: `resultType: "task"`, creación durable antes del handle, `tasks/get`, `tasks/update`, `tasks/cancel`, auth por cada petición, cancelación **cooperativa**, expiración explícita y `isError` distinto de fallo del ciclo. Estos nombres y códigos proceden del **texto estudiado**; se deberá comprobar la versión normativa exacta antes de construir. Task cancel ACK **no acredita** que un efecto haya cesado, por lo que U1 sigue siendo relevante.

Para U8, el material propone un loop reflexivo tipo GEPA con restricciones y revisión de PR; descarta por razones de licencia un motor externo mencionado en la fuente. **NO_DATA(external_licensing_and_latest_spec_not_independently_revalidated_here)**; no importar código.

Para U9, el estudio señala Playwright MCP y Chrome DevTools MCP como referencias de aislamiento, snapshot de accesibilidad y gestión de pestañas; **no** atribuye prueba física con lectores reales ni disponibilidad instalada.

## VI · Matriz de decisiones y prioridades

La Parte 2 conserva P1–P7 y N1–N11 y añade **N12–N15**:

- **N12 — tareas asíncronas duraderas:** KEEP semántica nativa, implementación HOLD hasta compatibilidad MCP, sin superservicios.
- **N13 — evolución de prompts y skills:** KEEP revisión con gates, secret detection y preservación semántica; HOLD producto, sin autoaplicación.
- **N14 — navegador/a11y determinista:** KEEP aislamiento y snapshots; HOLD dependencias hasta versión/licencia exactas.
- **N15 — CAMALEÓN v0.3:** PROPOSED; pendiente del texto de la Parte 3/3 y la confrontación con contratos vigentes.

Patrones anteriormente discutidos como Temporal, OpenCode, Hermes y Orca continúan siendo **comparaciones de diseño**, no autorización para sustituir scheduler, MCP o APP. Cualquier material de forks ofensivos retirados sigue `DISCARD` de código; solamente concepto defensivo para pruebas aisladas.

## VII–VIII · Cuestiones y límites no negociables

- ¿Dónde se verifica de manera atómica que el token sigue vigente en el **receptor del efecto**?
- ¿Qué significa `complete=true` cuando licencia, titular o permiso cambian entre páginas?
- ¿Quién puede marcar una skill `pinned/locked` sin evitar revisión del juez?
- ¿Cómo preservar certeza sobre tareas canceladas, revocadas o caducadas?
- ¿Cómo impedir que una evaluación de prompt ingiera secretos o reutilice instrucciones externas como autoridad?
- ¿Cómo separar un snapshot semántico del navegador de una prueba física de voz?
- ¿Cómo resolver la denominación del dominio F sin crear una identidad duplicada?
- ¿Cómo acreditar que el archivo fusionado existe **en el destino exacto**, no solo en otra rama?

**No datos aún verificados:** autonomía E2E de N/O, MCP Tasks efectivo, skills autoproducidas, lectores físicos, energía atribuible, licencias/versions exactas de todas las referencias y la Parte 3/3. La disponibilidad **documental** de los contratos N/O queda resuelta con esta fuente, pero su ejecución sigue `NO_DATA(no_e2e_accreditation)`.

## Condición de adopción privada

Antes de cambiar un contrato real: recuperar HEAD, propietario y PR vigente; verificar código existente; reservar una ruta sin solapamiento; crear un delta mínimo reversible y su fixture; obtener juicio independiente; **decisión soberana** para cada autorización reservada. Las fichas de los doce titulares siguen siendo la primera superficie de trabajo. La Parte 2 no les concede nuevos ámbitos ni promueve N/O a agentes LIVE.

**Conclusión:** la aportación más significativa de esta entrega es una arquitectura de **observación de fuentes + cuarentena + adopción con evidencia**, junto con cuatro deltas de continuidad avanzada. Se puede estudiar y documentar ya; su implementación depende de contratos, fuentes y pruebas aún por acreditar.
