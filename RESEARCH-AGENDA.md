# Agenda de investigación · SWARM (26-11-2026)

Documento público, conceptual y saneado. **No es una comisión ni un permiso de ejecución.** Cada propuesta requiere comparación con código existente, prueba y juicio independiente antes de cualquier cambio privado.

## Qué se ha observado y qué falta

| Eje | Existe / se reutiliza | Hueco verificable | Pregunta para investigación |
|---|---|---|---|
| Recuperación | CAMALEÓN, recibos, contratos de continuidad | Recuperar contexto no acredita sesión/GOAL ni capacidad de enviar | ¿Cómo recuperar tareas sin suplantación ni nuevas autoridades? |
| Inventario | MCP nativo y adaptador existentes | Paginación integrada como código en un corte histórico; inventario completo del servicio conectado y versión negociada NO_DATA | ¿Cómo probar completitud y revocación entre páginas? |
| Gobierno | CLAIM, grants, roster, gates, juez | Un PASS sintético no prueba ejecución real | ¿Cómo formalizar evidencia de autorización y resultado? |
| Memoria | Grafo tectónico y plan_store | Consistencia entre snapshots, commits y recibos | ¿Cómo resolver conflictos de versión y dependencias? |
| Concurrencia | Scheduler con DAG y presupuestos | Costes estimados no son energía ni latencia real | ¿Qué benchmark reproducible cuantifica utilidad por recurso? |
| Modelos | Catálogo, admisión y pruebas de elegibilidad | Callback de confianza sintético no equivale a atestación | ¿Qué evidencia independiente exige una admisión de modelo? |
| Accesibilidad | Proyección HTML/Acho y controles estáticos | Audio físico y paridad semántica E2E no acreditados | ¿Cómo demostrar equivalencia voz/pantalla/API? |
| APP | Interfaz y proyección de roles | Referencias visibles no demuestran agentes LIVE | ¿Qué cadena de procedencia debe mostrarse al usuario? |
| Observabilidad | Recibos, CI y telemetría | No existe métrica completa de VU/Wh o atención humana | ¿Qué instrumentación mínima basta sin vigilancia intrusiva? |
| Coordinación | NEXO, GitHub y Mesa | Duplicados, revisiones y estados históricos | ¿Cómo hacer FAN-IN determinista y sin trabajo repetido? |

## Deuda arquitectónica que conviene estudiar

1. **Contrato histórico vs realidad:** algunos documentos antiguos describen solo A–H o asignan a E/G/H nombres previos. Las fichas actuales A–K/NEXO y las propuestas L/M/P deben conservar versión y procedencia; no borrar historia ni tratarla como estado vivo.
2. **Aceptación incompleta:** 17 pruebas de adaptación pueden quedar en SKIP cuando falta el adaptador real. No se convierten en PASS; identificar qué contrato prueba cada una.
3. **Juez separado:** reproducir una prueba propia no equivale a validación independiente de otra implementación.
4. **Recepción durable:** no declarar COMPLETED_VERIFIED por ACK, RESULT sin testigo, comentario o CI aislada.
5. **Paginación MCP:** snapshot, cursor, límite de bytes, redacción, revocación, cambios concurrentes y completitud son requisitos distintos.
6. **Reutilización:** aprovechar APP plan_store, superbot_relevo, grant_journal; SWARM roster/scheduler; LAB journal; MCP existente. Evitar un segundo bus, orquestador, base de datos o servicio.

## Protocolo para cada investigación externa

Para cada idea, entregar: **problema → evidencia local saneada → proyecto/paper externo y licencia → diferencia con lo ya construido → adaptación mínima → métrica y baseline → riesgos → prueba adversarial → decisión KEEP/HOLD/DISCARD → siguiente unidad**.

No copiar código sin revisar licencia y dependencias. No publicar datos privados ni inferir que una herramienta externa funciona en PreceptorOS sin reproducirla.

## Preguntas prioritarias para el Soberano

- ¿Cuál es la unidad mínima de *trabajo útil verificado*? ¿Cómo se distingue de un comentario o commit?
- ¿Qué debe enseñar Acho cuando un agente está asignado, conectado, bloqueado o verificado?
- ¿Cómo autorizar/revocar por voz una acción concreta sin que la voz libre sea un grant?
- ¿Qué debe ocurrir si el MCP se conecta pero su inventario está incompleto?
- ¿Cómo medir la mejora de R5 antes de planificar R6?
- ¿Qué duplicidades documentales pueden eliminarse sin perder trazabilidad histórica?
- ¿Qué decisiones deben permanecer reservadas al Soberano incluso si hay ejecución autónoma?

## Actualización de prioridades · capacidades y MCP (26 noviembre)

**Estudio central:** [capacidades, endurecimiento MCP y pruebas reproducibles](AGENT-CAPABILITIES-MCP-2026-11-26.md). Esta agenda anterior es contextual y no certifica versiones desplegadas.

La investigación debe priorizar, en este orden, **P0 exclusión de escritor obsoleto en el punto de efecto**, **P0 integridad/caducidad temporal del inventario MCP**, **P1 procedencia real del iniciador y resultado duradero**, **P1 verificación de filtros/bytes del consumidor**, y **P2 paridad accesible y métricas de utilidad**. Para cada capacidad exigir prueba adversarial con oráculo y fuente exacta; no añadir nuevos agentes para sustituir un contrato incompleto.

**Separación obligatoria:** código en repositorio ≠ candidato en PR ≠ servicio conectado ≠ prueba E2E. Los tests sintéticos no demuestran permisos, inventario íntegro servido, voz física o independencia criptográfica del juez. `NO_DATA(causa)` cuando falte evidencia.

## Actualización empírica · seis carriles CAMALEÓN (26NOV2026)

La [síntesis StrongDM/P1–P7](CONTINUIDAD-AGENTIC-SWARM-2026-11-26.md) añade evidencia **agregada y saneada**. No modifica el mandato de estudiar antes de implementar.

| Prioridad | Cambio respecto al corte inicial | Hipótesis falsable para estudio externo |
|---|---|---|
| P0 · Propiedad del efecto | Se reprodujeron escrituras obsoletas y carreras en fixtures aislados; el almacenamiento durable parcial no basta. | Token monótono validado atómicamente por el receptor; ninguna escritura anterior logra efecto tras sustitución/revocación. |
| P0 · Autorización temporal | La paginación en fixtures mejoró, pero la validez puede cambiar durante la construcción de una respuesta. | O bien se acredita snapshot/linealización, o el inventario falla cerrado; ninguna fila caducada se presenta como autorizada. |
| P0 · Testigo independiente | Los resultados sintéticos del roster siguen sin demostrar el vínculo total entre la unidad y el resultado duradero. | El juez recupera un recibo tras reinicio y lo vincula a la operación concreta sin texto explicativo del constructor. |
| P1 · Consumidor accesible | Se encontraron respuestas aparentemente completas pese a filtros o presupuesto incompatibles. | La proyección rechaza una entrada no conforme y mantiene estado/cause/source/time coherentes en tres canales. |
| P1 · Entrega de documentos | Se observó un merge a rama intermedia que no propagó archivos al main de consulta. | Prueba de presencia/hash de archivos en el destino exacto, además de estado MERGED. |
| P1 · Aceptación | Persisten casos SKIP por integración todavía no conectada. | Los gates solo pasan si hay prueba de integración o evidencia equivalente aprobada, nunca ocultando SKIP. |
| P2 · Medición | Wh y minutos de atención activa aún no cuentan con baseline atribuible. | VU/Wh medido y estimado en series separadas; tiempo humano medido como interacción activa. |

**Regla de lectura:** una fixtura adversarial que encuentra un contraejemplo es un **FAIL del sistema bajo prueba**, aunque la prueba que lo detecta funcione. La ausencia de evidencia real de servicio o voz se marca `NO_DATA(causa)`, no PASS.

**Siguiente ciclo público:** pedir a proyectos externos ejemplos mínimos de compare-and-swap + fencing del **efecto**, cursores coherentes bajo revocación/tiempo, y pruebas falsables de accesibilidad; evaluar cada candidato por integración mínima, licencia, reversibilidad y coste de gobierno. El patrón StrongDM sirve para contrastar atributos, no autoriza desplegar software propietario.

## Ronda PRE-R6 · MVP nativo y skills por dominio

**Fuente:** [contratos propuestos para doce dominios](MVP-NATIVO-SKILLS-12-DOMINIOS-2026-11-26.md). La evolución documental de A–K y NEXO-09 es trabajo distribuido **propuesto/iniciado**, no doce implementaciones ni procesos de ejecución acreditados. R5 cerrado administrativamente por decisión humana; aceptación técnica HOLD. R6 PLAN ONLY y R7 no activada.

**Preguntas de la ronda:** ¿cuál es la capacidad existente que cada dominio puede reutilizar? ¿Qué skill mínima reduce pasos manuales sin inventar un plano de control? ¿Quién es el titular de su ficha, su interfaz y su prueba? ¿Qué evidencia falta para pasar de propuesta a componente comprobado? ¿Cuánto tiempo humano y energía se ahorra realmente, con denominador y método?

**Gate documental de una ficha:** identidad y misión intactas; `EXISTING/REUSE/PROPOSED/HOLD/DISCARD` separados; cada skill con `trigger/inputs/outputs/existing_tool/required_authorization/deny_conditions/evidence/tests/metrics/rollback`; enlaces internos válidos; revisión ajena; ningún secreto ni grant por texto. **No** adoptar por anticipado agentes o deltas anunciados en partes de investigación aún no disponibles.

**Tareas de contraste externo:** ejemplos reproducibles de actor single-writer sin proceso adicional; curación de skills bloqueadas y anti-drift; aislamiento de worktrees sin colisión; acceso default-deny con atribución verificable; verificación de lectores de pantalla sin depender solo de test unitario. Cada referencia necesita licencia/versión exacta antes de copiar o integrar.

## Preparación Ideas26nov Parte 3/3 · reconciliación de doce dominios

**[Guía de traspaso para redactar Parte 3/3](PREPARACION-IDEAS26NOV-PARTE3-2026-11-26.md)**. El estudio recoge los temas anunciados (MCP Tasks, evolución supervisada de prompts/skills, aislamiento de navegador y delta CAMALEÓN v0.3) y sus **puertas**, no una supuesta fuente recibida. Al corte se identificaron doce PR documentales, dos integradas y diez pendientes de juicio; ninguna PR equivale a skill funcionando E2E. Comprobación del esquema uniforme, incluido `deny_conditions`, y pruebas históricas de correlación RESULT/aceptación permanecen abiertas.

**Condición previa a una propuesta implementable:** recibir Parte 3 íntegra, confrontar método/nombres/licencia con fuentes exactas, recuperar HEAD/owner y proponer mínima adaptación reversible; mantener separados `SOURCE`, `VERIFIED` e `INFERENCE`. No suplantar contrato vigente ni convertir los posibles N/O en procesos activos.
