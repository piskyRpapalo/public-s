# Ideas26nov v0.3 · Parte 3/3 y Adenda A3 · contraste público previo a la ronda 4

**Corte documental:** 26 noviembre 2026. **Estado:** `SOURCE_RECOVERED / PROPOSED / NOT_DEPLOYED`. Esta página es una **síntesis saneada** de la tercera entrega de Ideas26nov, cotejada a nivel de principios con los contratos existentes de SWARM por Codex. No reproduce correo, mensajes de Mesa, rutas internas, datos de host, claves ni recibos privados. La Parte 3 y la Adenda A3 **han sido recibidas y leídas**; las Partes 1 y 2 se sintetizaron anteriormente. El estudio externo carecía de acceso al ground truth privado. **SOURCE** es referencia; **VERIFIED** exige pruebas privadas independientes y no se presume; **INFERENCE** es adaptación a evaluar.

Fuentes de continuidad: [StrongDM/P1–P7 (Parte 1)](CONTINUIDAD-AGENTIC-SWARM-2026-11-26.md), [N/O y U0–U10 (Parte 2)](IDEAS26NOV-V03-PARTE2-N-O-U0-U10.md), [12 dominios y skills propuestas](MVP-NATIVO-SKILLS-12-DOMINIOS-2026-11-26.md), [plantilla de manifiesto](MANIFEST-TEMPLATE.md).

## 1. Ground truth frente a la propuesta

| Proposición externa | Contraste conceptual con el SWARM existente | Adaptación y límite |
|---|---|---|
| Crear un nuevo contrato CAMALEÓN v0.3 | Ya existe CAMALEÓN con `READ_CONTEXT`, `CONTINUE_UNIT`, `RETURN`, identificación del ejecutor, gates y recibo. | **EXTEND**, no sustituir. La plantilla externa no tiene autoridad por sí sola. |
| «Web no puede CONTINUE_UNIT» absoluto | El contrato real distingue recuperar contexto, operar sobre una CLI administrada por una herramienta autorizada y pretender heredar la identidad de otro proceso. | **CONFLICTO**: prohibir herencia y control no acreditado, **no** denegar por etiqueta todas las solicitudes Web que pasen autorización efectiva. |
| `taskId` para recuperar tareas largas | Ya hay sesión, autorización, correlación y recibos; no está acreditado que el servicio existente negocie MCP Tasks. | **PROPOSED U7**: integración opcional en transporte único; handle ≠ grant. |
| Autoevolución continua de prompts y skills | Hay fichas, evaluación, control de cambios y revisión; no hay evidencia E2E de un motor de evolución implantado. | **PROPOSED U8**: candidatos aislados, datos saneados, pruebas, revisión ajena y decisión humana; cero autoaplicaciones. |
| Snapshots accesibles de navegador y perfiles aislados | Hay una interfaz y una proyección semántica; snapshot sintético ≠ voz o lector físico verificado. | **PROPOSED U9**: reutilizar APP y sus tests; no instalar otro frontend ni declarar accesibilidad física. |
| Reescribir todos los MD y prompts | Las doce fichas de dominio ya tienen MVP y skills propuestos; sustituirlas replicaría trabajo. | **HOLD U10**: diferencias por requisito, propietarios, cambios mínimos, digest+rollback y verificación de presencia en destino real. |
| N · VIGÍA / O · ADUANA | Tienen contratos de estudio desde Parte 2, no prueba de ejecución como procesos ni grants. | **PROPOSED**; reutilizar herramientas y revisores existentes. La fuente nueva por sí sola no activa agentes. |

**Corrección verificable del corte:** las **12 fichas documentales** de los dominios A–K y NEXO-09 fueron incorporadas a la rama principal del SWARM al finalizar la ronda de preparación. **No equivale a 12 skills invocables ni 12 trabajadores activos.** La comprobación de suites sintéticas indicó en un HEAD concreto **225 PASS, 2 FAIL de correlación de resultados y 17 SKIP de aceptación**; el denominador se aplica solo al corte observado, no a todas las ramas actuales. La aceptación técnica de R5 continúa HOLD; el ciclo administrativo fue cerrado por decisión soberana, R6 sigue PLAN ONLY y R7 no activada.

## 2. U7 · MCP Tasks como capacidad opcional, no segundo servicio

La Parte 3 plantea tareas asíncronas duraderas con `resultType: "task"`, `taskId`, `tasks/get`, `tasks/update`, `tasks/cancel`, estados de tarea y expiración. El diseño debe distinguir la persistencia del **handle** de la vigencia del **permiso**: cada consulta/actualización/cancelación requiere comprobación efectiva. La cancelación puede ser cooperativa: su ACK **no prueba que el trabajo haya dejado de producir efectos**; el receptor tiene que rechazar un escritor obsoleto.

Pruebas falsables: entrega del handle solo después de persistencia, recuperación tras interrupción, cliente sin capacidad negociada, expiración y revocación, task de otro principal denegada, cancelación tardía y distinción entre error de herramienta y fallo de ciclo. El inventario de sesiones y GOAL no se sustituye por Tasks.

**Decisión:** KEEP semántica, HOLD implementación, `NO_DATA(negotiated_tasks_runtime_and_E2E_unverified)`. Consultar la versión normativa y licencias exactas antes de modificar código.

## 3. U8 · Aprendizaje de skills supervisado, no auto-mejora incondicional

Se estudian mecanismos de evolución reflexiva como GEPA/Hermes: extraer **muestras saneadas**, producir variantes `PROPOSED`, ejecutar oráculos y pruebas, comprobar preservación semántica y tamaño, publicar una PR y exigir un juicio humano/independiente. `pinned` y `locked` requieren dueño y capacidad de desbloqueo definidos; nunca deben permitir evadir revisión. Ni los prompts ni el ejecutor cambian a mitad de una operación autorizada.

Señales mínimas: **0 variantes autoaplicadas, 0 secretos expuestos en datasets, 0 expansiones de permisos por deriva y 0 entregas no presentes en el destino verificado**. Son **objetivos, no resultados medidos**. Los claims de estrellas, versiones, precios y licencias de la fuente se verifican en el origen antes de reutilizar código; no usar popularidad como prueba.

**Decisión:** KEEP patrón con puerta; HOLD producto y dependencias, `NO_DATA(independent_fitness_and_runtime_not_accredited)`.

## 4. U9 · Navegador aislado y accesibilidad verificable

Patrones investigados: Playwright MCP, Chrome DevTools MCP, snapshots de accesibilidad, contextos aislados por titular, control de una pestaña por actor, revocación y denegación de cambios globales. La fuente externa no demuestra versión/licencia exacta instalada ni que la UI existente use esas herramientas.

La adaptación a Acho parte de un único objeto `state/cause/source/observed_at/evidence_ref`, proyectado de manera **semánticamente equivalente** a pantalla, voz y salida máquina. La prueba sintética de snapshot se evalúa por separado del lector físico (TalkBack, NVDA o equivalente). El DOM y el contenido de páginas se tratan como datos no confiables.

**Pruebas:** dos contextos sin transferencia de cookies, control de pestaña obsoleto rechazado, browser-wide deny, busy→HOLD, captura que no maquilla incertidumbre y lector físico autorizado. **Decisión:** KEEP patrón, HOLD herramientas hasta comprobar licencia, `NO_DATA(browser_isolation_and_physical_reader_E2E)`.

## 5. U10 · CAMALEÓN v0.3 por diferencias y gates

**Conservar:** `READ_CONTEXT` reversible; `CONTINUE_UNIT` solo con autorización real, sesión/alcance vigentes y sin herencias; `RETURN` explícito; atribución del ejecutor; recibos y `NO_DATA(causa)`.

**Añadir solo después de contrastar:** handles persistidos cuando Tasks exista, triple evidencia de iniciador sin inventar firma, separar ventana de autorización, lease/writer turn y TTL de transporte, verificación de fencing en el receptor, etiquetado SOURCE/VERIFIED/INFERENCE, guardas anti-inyección, mecanismo propuesto→revisado→aprobado, digest de baseline y rollback, prueba de presencia de la versión final en `main`.

**No adoptar:** Web→CLI prohibido globalmente, un task handle como grant, ACK de cancelación como parada, TTL de transporte como sustituto de expiración de permisos, eliminación de RETURN, cambios automáticos del arranque ni modificación no coordinada de fichas de dominio.

**Decisión:** `PROPOSED/HOLD` antes de cambios de contrato. El autor externo carecía del texto privado vigente. La reconciliación por secciones sí puede prepararse, pero todo cambio normativo requiere propietario, diff contra baseline efectivo, juez independiente y decisión soberana concreta.

## 6. Adenda A3 · defensa antes de activar herramientas externas

La Parte 3 incluye una Adenda A3 sobre revisión y refutación de hallazgos, riesgos de supply chain de skills, detección de secretos, red team de múltiples turnos y oráculos deterministas. Se asignan a **responsabilidades existentes**, no cinco nuevos servicios.

| Función de diseño | Patrón externo a estudiar | Adaptación mínima al dominio existente | Gate |
|---|---|---|---|
| Juicio de hallazgos | cloudflare/security-audit-skill | D revisa cada hallazgo intentando refutar falsos positivos sobre HEAD final | Sin replay/HEAD exacto → HOLD |
| Seguridad de skills | NVIDIA/SkillSpector | Evaluación documental en O propuesta, con fixtures J/K de inyección | Fuente/firma/licencia no verificadas → HOLD |
| Secretos en datasets | TruffleHog | Saneado previo a minería con **secretos sintéticos**, sin verificar secretos reales con terceros | Secreto sintético detectable en dataset → FAIL |
| Red team multivuelta | Microsoft/PyRIT | J diseña ataques **aislados** a reglas propias y mide si se observa la inyección | No se aplicó el ataque → `NO_DATA(injection_not_applied)` |
| Oráculos deterministas | Trivy, Nuclei, Semgrep | K contrapone reglas explícitas al juicio D, sin instalación por defecto | Sin regla ejecutada → NO_DATA |

**O · ADUANA:** el resumen anterior de Parte 2 solo citaba cinco skills `o.*` y omitió `o.secret_detection`, presente en la Adenda A3. El catálogo correcto **a nivel propuesto** pasa a **seis**: `o.pattern_quarantine`, `o.license_gate`, `o.fork_divergence_audit`, `o.injection_probe`, `o.ficha_patron` y `o.secret_detection`. Ninguna es API operativa verificada.

Los productos de seguridad externos, escáneres y frameworks no se instalan ni clonan para esta revisión. Las licencias y versiones citadas por terceros siguen pendientes de revisión independiente. El código de forks ofensivos retirados permanece DESCARTADO; no ejecutar ataques reales ni probar credenciales vivas.

## 7. Puente a la ronda 4

**Inconsistencia de fuente:** el mensaje se identifica como **«Parte 3 de 3»** pero su Adenda A3 menciona una **«Parte 4»** y unidades **U11–U14** que **no aporta**. Por tanto, `NO_DATA(source_round4_U11_U14_text_not_received)`. Este documento no deduce su definición de nombres sugeridos ni genera agentes para esos números.

Cuando llegue la siguiente entrega, debe indicar versión, fuentes, nuevos requisitos, dueños, si U11–U14 son unidades reales o solo una referencia editorial y qué obligaciones nuevas propone. Se comparará con las doce fichas existentes y la reconciliación privada, preservando el contrato canónico hasta juicio y autorización.

**Resumen:** Parte 3 y A3 están recibidas; las propuestas U7–U10 y defensa se pueden estudiar y verificar sin activar productos nuevos. La ronda 4 se prepara sobre **evidencia y fuentes**, no sobre contratos inventados.
