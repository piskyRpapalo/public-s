# SWARM · MVP nativo y catálogo de skills · doce dominios (PRE-R6)

> **Corrección posterior de continuidad · 26NOV2026:** los doce dominios A–K + NEXO-09 fueron incorporados como **fichas documentales** en el `main` del SWARM. La cifra anterior «dos integradas y diez abiertas» es un corte histórico, no el estado final de esas PR. Ideas26nov Partes 1–3 ya constan recibidas documentalmente; la **Parte 4 y U11–U14** siguen `NO_DATA(source_not_received)`. [Preparación de la Ronda 4 · visión, CineK y continuidad](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md). **S/T candidatas, no nuevas identidades aprobadas; L conserva evaluación de utilidad.** No se atribuyen aquí doce skills E2E.

**Estudio público, 26 de noviembre de 2026.** Documento de investigación y propuesta de contratos; no es una comisión ni una transcripción del entorno privado. Describe doce **identidades de referencia** (once A–K más coordinación NEXO-09), no doce procesos CLI acreditados, ni doce servicios a instalar. Los doce carriles conversacionales se han propuesto para trabajar **en paralelo y sobre fichas separadas**. La incorporación a Markdown privado no crea capacidades ejecutables.

**Decisión de alcance:** `R5_WORK_CYCLE=CLOSED_ADMINISTRATIVELY_BY_SOVEREIGN`, `R5_TECHNICAL_ACCEPTANCE=HOLD`, `R6=PLAN_ONLY` y `R7=NOT_ACTIVATED`. El cierre de gestión no promueve errores, SKIP o `NO_DATA` a PASS ni libera gates de seguridad. Los estados son **declaraciones documentales**, no telemetría live.

## 1. Principio de evolución: mejorar el propio dominio, no multiplicar agentes

Arquitectura objetivo: decisión humana soberana → coordinación y recuperación de contexto → MCP y herramientas autorizadas → ejecutores dentro del alcance vigente → resultado y recibo duradero → juez separado → Acho con **el mismo estado semántico** en voz, pantalla y datos.

**RECOVER → STUDY → ADAPT → DOCUMENT → VERIFY.** Cada rol inspecciona primero el código, la documentación, la ruta propietaria y los recibos existentes; distingue implementación, conexión y prueba E2E; propone la **mínima adaptación reversible**. El trabajo paralelo requiere CLAIM documental y propiedad cooperativa de archivos; esa reserva no sustituye un control de exclusión atómica en el receptor de los efectos.

### Estados que deben aparecer en toda ficha

| Estado | Evidencia mínima | No implica |
|---|---|---|
| **EXISTING** | Fuente y ruta del componente ya construido, versión observada | Que el servicio esté disponible |
| **REUSE** | Contrato de componente reutilizable y punto de adaptación | Permiso para cambiarlo |
| **PROPOSED** | Problema, owner, interfaz, riesgo, métrica y fixtures | Skill ejecutable |
| **IMPLEMENTED** | Código + pruebas reproducibles sobre versión exacta | Servicio conectado |
| **CONNECTED** | Integración comprobada con identidad y alcance | Ciclo de trabajo completo |
| **WORKING** | Acción y resultado correlacionados con evidencia | Validación independiente automática |
| **COMPLETED_VERIFIED** | Testigo E2E, replay independiente y canal accesible cuando aplique | Que todas las demás skills estén verificadas |
| **HOLD / NO_DATA(causa)** | Fallo o evidencia ausente, fuente y condición de salida | PASS implícito |

## 2. Doce MVP de dominio y skills nativas propuestas

Los IDs son **identificadores de diseño**. No aseguran que existan actualmente funciones, comandos MCP o servicios con esos nombres.

| Carril | MVP nativo mínimo | Skills conceptuales (PROPOSED salvo prueba contraria) | Reutilización deseada | Prueba falsable |
|---|---|---|---|---|
| **NEXO-09 · coordinación** | Reconciliar una unidad entre fichas, CLAIM, PR, tests y recibo con el mismo propietario | `nexo.claim_audit`, `nexo.dependency_fan_in`, `nexo.delivery_presence_check` | Repositorio de contratos, historial de versiones y recibos | Dos propuestas de la misma unidad no generan dos propietarios; PR fusionada a rama intermedia no se declara en main |
| **A · mando** | Clasificar una intención en propuesta/abstención sin despachar | `a.intent_classify`, `a.scope_explain`, `a.ambiguity_abstain` | Parser y contrato de intención existentes | 0 falsos despachos ante órdenes ambiguas o contexto manipulado |
| **B · pulso** | Asociar operación, sesión, CLAIM, autorización, efecto y recibo duradero | `b.witness_binding`, `b.claim_conflict_probe`, `b.replay_reconcile` | Roster, journal y testigos existentes | Escritor obsoleto y doble CLAIM rechazados en el **punto de efecto**, incluso tras reinicio |
| **C · memoria tectónica** | Recuperar contexto con procedencia y regenerar derivados sin cambiar canon | `c.provenance_recover`, `c.contract_diff`, `c.snapshot_verify` | Grafo, historial de versiones y generadores existentes | Derivado byte-a-byte correspondiente a su fuente; contexto no hereda writer ni grant |
| **D · juez** | Reproducir una afirmación sobre versión exacta sin depender de la narración del constructor | `d.independent_replay`, `d.bias_probe`, `d.gate_audit` | Runner de pruebas, evidencias normalizadas, CI | Código roto con argumento convincente sigue fallando; ninguna prueba omitida cuenta PASS |
| **E · caudal MCP** | Inventario íntegro o error explícito bajo alcance y presupuesto | `e.inventory_walk`, `e.initiator_evidence`, `e.temporal_scope_check` | Transportes, cursor y permisos existentes | Revocación, expiración, reloj adversarial y cambios de filtro no producen `complete=true` falso |
| **F · VECTOR** | Planificar unidades paralelas independientes respetando presupuestos y owners | `f.dag_split`, `f.worktree_scope`, `f.budget_guard` | Scheduler, DAG, ramas/PR y roster existentes | Colisión de dos carriles detectada; no sobrepasar capacidad ni crear scheduler nuevo |
| **G · expertos** | Evaluar un especialista/modelo con trazabilidad sin promocionarlo por una métrica aislada | `g.model_inventory`, `g.eligibility_check`, `g.provider_terms_review` | Catálogo de modelos y harness de elegibilidad | Versión, licencia, digest y muestra ciega; sin datos: no admisión |
| **H · Acho** | Anunciar estado y causa de una unidad igual en pantalla, voz y máquina | `h.canonical_state`, `h.accessible_status`, `h.partial_inventory_guard` | APP y proyección existentes | 100 eventos con paridad semántica; lector físico probado por separado |
| **I · APP-PUENTE** | Mostrar una unidad y solicitar una acción al punto de permiso existente, sin falsa sesión LIVE | `i.conversation_projection`, `i.authorized_action_preview`, `i.recovery_ui` | APP, Talk, interfaz y mecanismos de autorización existentes | Propuesta ≠ autorización ≠ ejecución ≠ resultado; revocación visible en todos los canales |
| **J · Red Team** | Crear contraejemplos aislados para contratos sin tocar activos reales | `j.identity_spoof_fixture`, `j.stale_writer_probe`, `j.injection_harness` | Tests, sandbox y entornos sintéticos existentes | Detectar denegaciones defectuosas; inyección no aplicada = `NO_DATA` |
| **K · Blue Team** | Contener y restaurar una unidad con permisos mínimos y sonda final | `k.policy_deny_probe`, `k.revoke_restore`, `k.rollback_verify` | Políticas, registros y fixtures existentes | Una partición/caída no habilita best-effort; recuperación demostrada por sonda |

**Alcance de identidades:** L (utilidad), M (meta-juicio) y P (política) son **capacidades documentales propuestas**, no procesos nuevos. R no añade un segundo Red Team. Otras identidades mencionadas en estudios incompletos no se activan antes de disponer de su contrato y decisión.

## 3. Contrato uniforme de skill propuesta

El mínimo que debería contener cada ficha Markdown, **antes de programar**:

```yaml
skill_id: "dominio.identificador"
owner_role: "A..K|NEXO-09"
state: "PROPOSED" # no función ni permiso ejecutable
purpose: "problema concreto y verificable"
trigger: "evento de entrada documentado"
inputs: ["datos de entrada normalizados, sin secretos"]
outputs: ["resultado", "estado", "causa", "fuente", "hora", "evidence_ref"]
existing_tool_or_mcp: "REUSE | NO_DATA(tool_not_verified)"
effective_scope: "del permiso vigente de la sesión, no del CLAIM"
required_authorization: "verificar en el punto de acción"
deny_conditions: ["principal no acreditado", "grant/revocación/alcance inválidos", "evidencia incompleta"]
evidence_source: "HEAD exacto + prueba + recibo"
test_plan: ["determinista", "adversarial", "integración", "E2E si aplica"]
metric: "numerador/denominador y baseline"
risk_and_rollback: "límite de efecto, reversible, sin nuevo plano de autoridad"
dependencies: ["owner y contrato"]
next_piece: "adaptación mínima por PR revisable"
```

El `owner_role` es dueño **documental** del contrato de skill, no principal privilegiado. `CLAIM` no concede grant, `READ_CONTEXT` no reanuda writer CLI y un prompt no genera una aplicación instalada.

## 4. Arquitectura de referencia en cuatro fronteras

**Frontera 1 — intención y política:** el usuario solicita; el rol A clasifica; cualquier acción consecuencial exige una autorización real y vigente. El patrón StrongDM aporta estudio de atribución y política por llamada, **no adopción de su broker propietario**.

**Frontera 2 — continuidad y exclusión:** C recupera contexto; B/NEXO coordinan CLAIM y reciben resultado; F evita solapamiento cooperativo. Para prevenir al escritor zombie hace falta un mecanismo **monótono comprobado en el receptor del efecto**. Un lock en un comentario GitHub y un TTL del proceso no acreditan seguridad.

**Frontera 3 — evidencia y juez:** todo resultado debe enlazar operación, principal demostrado, momento del efecto, recibo y versión. D reproduce el oráculo independientemente. Un ACK, mensaje o CI parcial no equivalen a `COMPLETED_VERIFIED`.

**Frontera 4 — accesibilidad:** H e I deben proyectar `state/cause/source/observed_at/evidence_ref` en un lector visual, uno auditivo y uno de máquina. Pruebas sintéticas aseguran parte del contrato, **no** sustituyen TalkBack, VoiceOver u otros lectores físicos.

## 5. Pruebas adversariales y métricas transversales

| Puerta | Test mínimo | Métrica |
|---|---|---|
| Unicidad y autorización | Dos escritores, interrupción, revocación, reinicio y token obsoleto | 0 efectos obsoletos por 1.000 intentos; no certificar si solo hay fixture cliente |
| Inventario | Filtro por rol/estado, cursor, expiración, bytes UTF-8, altas/bajas | 0 falsos `complete`; filas declaradas = autorizadas, si hay oráculo |
| Identidad | Web se anuncia como CLI; contexto CAMALEÓN intenta heredar sesión | 0 falsas autorizaciones; `unknown` explícito |
| Juicio | HEAD con bug y relato convincente; paridad de runner | Falsos PASS y desacuerdos cuantificados |
| Accesibilidad | 100 estados revocados/parciales/indeterminados | 0 divergencias semánticas; pruebas físicas aparte |
| Intervención | Notificación, acción humana activa y decisión reservada | Minutos activos medidos, **no** latencia hasta respuesta |
| Energía | Contador local o estimación remota con método y ventana | VU/Wh medidos separado de VU/Wh estimados |
| Publicación Git | Merge a rama intermedia o enlace roto | 0 entregas declaradas sin presencia verificable en destino |

**Integridad de datos:** valores desconocidos se representan como `NO_DATA(causa)`, no `0`, `PASS` o `LIVE`.

## 6. Referencias e ideas externas contrastables

- [Patrón de StrongDM](https://docs.strongdm.com/ai): atribución, decisión por acción, denegación y auditoría; producto propietario, código del broker **no auditado**.
- [Temporal](https://github.com/temporalio/temporal) y [Kubernetes](https://kubernetes.io/docs/reference/using-api/api-concepts/): unicidad semántica y paginación coherente; **no** desplegar automáticamente esos productos.
- [celld](https://github.com/denoland/celld): concepto de actor/celda con titular único, **NO_DATA(exact_license_and_implementation_review)**.
- [OpenCode](https://github.com/anomalyco/opencode): consentimiento y denegación por defecto como concepto; no copiar código sin revisar licencia exacta.
- [Hermes Agent](https://github.com/NousResearch/hermes-agent): curator pin/lock, delegación por presupuesto, coste y procedencia de skills; estudiar el patrón, no instalar marketplace.
- [Orca](https://github.com/stablyai/orca): aislamiento de carriles por worktree y fuente de verdad en Git; evitar sumar DB/servicio por defecto.
- [ARIA APG](https://github.com/w3c/aria-practices): regiones de estado persistentes, un único registro canónico y ensayos con lector.
- **Forks de proyectos ofensivos retirados:** `DISCARD` de código; solo estudiar contramedidas con fixtures sintéticos, sin ejecutarlos.

Fuente de inspiración: un documento de ideas **v0.3, Parte 1/3**, más [continuidad y StrongDM](CONTINUIDAD-AGENTIC-SWARM-2026-11-26.md), [agenda](RESEARCH-AGENDA.md) y [capacidades MCP](AGENT-CAPABILITIES-MCP-2026-11-26.md). **Corte histórico al redactar esta ficha:** las Partes 2/3 y 3/3 aún no estaban disponibles, por lo que este documento base no afirmaba haber adoptado sus contratos, agentes ni prompts. **Actualización posterior:** la [Parte 2/3 ya fue recibida y sintetizada](IDEAS26NOV-V03-PARTE2-N-O-U0-U10.md); sus roles N/O y U0–U10 siguen PROPOSED. La [guía para la Parte 3/3](PREPARACION-IDEAS26NOV-PARTE3-2026-11-26.md) expone las dependencias sin inventar la fuente todavía ausente. Las 12 propuestas de dominio tienen PR documentales identificadas: dos verificadas en main y diez abiertas en un corte, sin nueva acreditación E2E.

## 7. Método de contribución

Cada titular de dominio puede proponer un cambio **en su propia ficha** tras recuperar contratos y trabajo previo, con rama/PR aislada, pruebas documentales y recibo. NEXO coordina; D revisa sin autocertificarse. Las doce unidades pueden comenzar en paralelo; un conflicto suspende **solo la escritura afectada** y se escala al titular. El Soberano conserva el control de firma, decisiones reservadas, grants y despliegues.

**Conclusión:** el MVP nativo de un dominio es un conjunto **pequeño, trazable y refutable** de contratos de skill que reutilizan herramientas existentes. Una docena de fichas no es una docena de servicios; una decisión administrativa de cerrar una ronda no equivale a aceptar técnicamente una capacidad.
