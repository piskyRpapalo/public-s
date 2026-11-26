# Continuidad agentic en SWARM · corte público del 26 de noviembre de 2026

**Ámbito:** síntesis pública y saneada de dos paquetes de investigación sobre StrongDM y siete patrones externos (P1–P7), contrastados con resultados **agregados** de dos rondas de trabajo paralelo. **No es una comisión, una implementación, un informe de seguridad productiva ni una autorización.** No contiene identificadores de sesiones, recibos privados, rutas de infraestructura, tokens, grants, datos de máquinas ni procedimientos de acceso.

## 1. Pregunta central

¿Cómo convertir seis conversaciones de preceptores que cooperan en un ciclo de trabajo útil, verificable y accesible, **sin convertir la coordinación en una autoridad nueva**?

Cadena objetivo: decisión humana soberana → coordinación autorizada → herramientas existentes → ejecutores dentro de sus permisos → resultados duraderos → juicio independiente → representación accesible visual, auditiva y de máquina.

**Resultado observado:** se organizaron seis carriles conversacionales con identidad determinista y recibos de continuidad: coordinación (NEXO), transporte (E), correlación (B), juez (D), accesibilidad (H) y memoria/contratos (C). Se publicaron resultados y se retomaron unidades en otra ronda. **Esto no prueba seis procesos autónomos ni un bucle E2E**; no hay evidencia pública suficiente de sesiones CLI vivas, permisos operativos completos o control por voz físico.

## 2. Qué cambió en el estudio

| Aspecto | Evidencia agregada o aprendizaje | Estado |
|---|---|---|
| Recuperación CAMALEÓN | La reanudación contextual evitó reconstruir trabajo ya incorporado; cada terminal mantuvo un slot definido y dejó recibo. | **WORKING como procedimiento documental**, no continuidad CLI acreditada. |
| Coordinación de seis carriles | Recibos separados permitieron detectar duplicidades, propietarios y dependencias. | **WORKING documental**; ejecución autónoma y exclusión atómica **NO_DATA**. |
| Inventario MCP | Paginación y comprobaciones de revocación mejoraron en fixtures; quedaron diferencias entre código y esquema efectivamente servido. | **IMPLEMENTED en código / CONNECTED parcialmente**; inventario completo E2E **NO_DATA**. |
| Vigencia temporal | El juez encontró resultados de inventario cuya validez podía cambiar durante la operación; un segundo contraejemplo cuestionó la suposición de reloj estable. | **FAIL sintético reproducible**, corrección candidata **HOLD** hasta juicio completo. |
| Unicidad de escritores | Se detectaron carreras y escrituras tardías en pruebas aisladas; un journal duradero no garantiza por sí mismo fencing en el receptor del efecto. | **FAIL sintético reproducible**; fencing efectivo **NO_DATA**. |
| Consumidor accesible | Pruebas de proyección conservaron paridad semántica, pero detectaron falsos estados de completitud ante filtros o presupuestos mal respetados. | **PASS parcial / FAIL adversarial**; lectores y voz reales **NO_DATA**. |
| Documentos fusionados | Una modificación podía constar como fusionada en una rama y, aun así, faltar del `main` que consultan los demás. | **FAIL de integración documental**; recuperación mediante revisión separada. |
| Aceptación | Un conjunto histórico de 17 casos seguía sin ejecutar por falta del adaptador pertinente. | **HOLD**; `SKIP` nunca equivale a `PASS`. |

**Estado general:** R5 puede continuar con correcciones focalizadas, pero **no está cerrado**. R6 es planificación condicionada; R7 no está activada. Ningún estado de este cuadro es una observación continua de producción.

## 3. Adaptación conceptual del patrón StrongDM

Referencia externa: [StrongDM Secure AI](https://docs.strongdm.com/ai), [AI Attribution](https://docs.strongdm.com/ai/ai-attribution) y [MCP Gateway](https://docs.strongdm.com/ai/mcp-gateway). La documentación sirve para estudiar autorización *just-in-time*, atribución del iniciador, intermediación de herramientas y auditoría por acción. **No se ha revisado el código interno propietario del broker; `NO_DATA(closed_source_not_reviewed)`.**

**KEEP del patrón; HOLD del producto.** La adaptación mínima deberá reutilizar las rutas de autorización y transporte existentes, no añadir un gateway SaaS o un segundo plano de mando.

Separaciones obligatorias:

- `initiator_claimed` no demuestra `initiator_verified`: un nombre, variable de entorno o encabezado aportado por el cliente puede ser falso.
- `CLAIM` reserva una unidad, pero **no es un grant**. Las facultades efectivas proceden del permiso real y se comprueban en el momento de actuar.
- `READ_CONTEXT` no hereda credenciales ni writer turn de otra sesión. Una conversación Web no se transforma en proceso CLI por recuperar su historia.
- La función de política propuesta deniega o expresa incertidumbre **dentro del punto de autorización existente**; no otorga nuevos privilegios ni reemplaza la decisión humana.
- El registro de evaluación debe asociar principal, acción, recurso, alcance, decisión, causa, fuente y versión sin exponer secretos.

**Prueba exigida:** identidad afirmada sin corroboración, recurso fuera de alcance, grant revocado o acción desde un modo no autorizado deben fallar cerrados; el juez reproduce la decisión a partir de evidencia, no del relato del ejecutor.

## 4. Siete patrones para investigación y adaptación mínima

| Patrón | Referencia pública | Adaptación mínima; no producto instalado | Prueba adversarial y métrica | Decisión |
|---|---|---|---|---|
| **P1 · CLAIM y escritor único** | [Temporal](https://github.com/temporalio/temporal), fencing/etcd | ID de unidad determinista; comprobar si el almacenamiento y el receptor del efecto aceptan una revisión monótona **atómica**. Un TTL no basta. | Dos escritores concurrentes, pausa y reanudación obsoleta; **0 escrituras antiguas aceptadas / 1.000 unidades**. | KEEP patrón; DISCARD añadir Temporal como servicio por defecto. |
| **P2 · Inventario íntegro** | [Paginación de Kubernetes](https://kubernetes.io/docs/reference/using-api/api-concepts/) | Cursor/snapshot o rechazo explícito ante cambio; jamás declarar completo por haber recibido solo una página. El código de error exacto depende del transporte, no se presupone HTTP 410. | Altas, revocaciones, corrupción, filtrado y presupuesto UTF-8 entre páginas; **0 falsos completos**. | KEEP semántica; sin segundo broker. |
| **P3 · Identidad CLI/Web** | [StrongDM Attribution](https://docs.strongdm.com/ai/ai-attribution), [ai-agent-detect](https://github.com/agent-detect/ai-agent-detect) | Evidencia por capas de herramienta/sesión/proceso; `unknown` explícito; no autorizar continuidad de escritor CLI solo por una etiqueta Web. | Suplantación Web, entornos heredados y sesiones anidadas; clasificación correcta y falsos ALLOW. | KEEP patrón; HOLD catálogos hasta revisar versión/licencia. |
| **P4 · Energía y atención** | [CodeCarbon](https://github.com/mlco2/codecarbon), [EcoLogits](https://github.com/mlco2/ecologits) | Diferenciar Wh medidos localmente de TDP o consumo remoto **estimados**; atención activa ≠ demora hasta responder a una notificación. | Recibo VERIFIED sin instrumento energético: `NO_DATA` de la métrica, no 0 Wh ficticios; medir VU/Wh y VU/minuto activo por separado. | KEEP metodología; HOLD nuevas dependencias hasta revisión exacta. |
| **P5 · Juez realmente independiente** | Literatura sobre fiabilidad de LLM-as-judge | Entrada normalizada, replay sobre versión exacta, runner distinto y control de sesgos de estilo/posición. Chat distinto no demuestra principal criptográfico distinto. | Código roto con explicación persuasiva debe seguir fallando; concordancia con oráculos humanos cuando exista muestra. | KEEP patrón; no añadir framework automáticamente. |
| **P6 · Incertidumbre accesible** | [W3C ARIA Practices](https://github.com/w3c/aria-practices), [MDN live regions](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Guides/Live_regions) | Una fuente canónica `state/cause/source/observed_at/evidence_ref`; semántica idéntica en voz, pantalla y API, sin imponer bytes idénticos entre formatos. | Filtros falsos, filas excesivas, repetición de anuncios y eventos desconocidos; **0 divergencias semánticas**; prueba física aparte. | KEEP. |
| **P7 · Recuperación segura** | [LitmusChaos](https://github.com/litmuschaos/litmus), [Chaos Mesh](https://github.com/chaos-mesh/chaos-mesh) | Fixturas aisladas de steady state, fallo inyectado y comprobado, aborto, reversión y sonda final. | Si no se inyectó realmente el fallo, resultado `NO_DATA(injection_not_applied)`, no PASS. | KEEP método; HOLD plataformas de caos. |

Las referencias externas aportan ideas **no equivalencias de implementación**. Antes de incorporar código o datos de terceros: revisar commit, licencia exacta, dependencias, superficie de ataque y condiciones de reversión.

## 5. Puertas de adopción y evidencia

- **E0 · PROPOSED:** hipótesis, fuente, responsable y manifiesto de cambio; **sin grant**.
- **E1 · IMPLEMENTED:** cambio concreto y pruebas deterministas sobre versión exacta.
- **E2 · CONNECTED:** la herramienta o consumidor accede a un servicio autorizado y puede declarar su cobertura/completitud; un ping no basta para inventario.
- **E3 · WORKING:** unidad útil con identidad y permiso comprobados, acción, resultado y recibo, sin deducción de evidencia faltante.
- **E4 · COMPLETED_VERIFIED:** replay independiente de la cadena completa y presentación accesible probada en los canales requeridos.

**Ojo:** estos niveles son una **propuesta de investigación** y no sustituyen la escalera o los gates canónicos del repositorio privado.

## 6. Tres correcciones prioritarias para la siguiente investigación

1. **Fencing real en el punto de efecto.** El almacén puede tener operaciones transaccionales y aun así permitir que un escritor antiguo produzca un efecto. Identificar el recurso que debe rechazar el token anterior; probar carrera, revocación y reinicio sin nuevo coordinador.
2. **Validez de inventarios durante toda su construcción.** Un cursor correcto no basta si una autorización cambia de estado antes de la entrega, y una comprobación entre dos lecturas de reloj puede pasar por alto cambios intermedios. Definir el punto de linealización, el modelo de tiempo y un fallo explícito seguro.
3. **Paridad con entrada adversarial.** La vista accesible no debe promover una respuesta como completa cuando contradice filtros, presupuesto o procedencia. Validar datos en el consumidor sin usar una UI verde como prueba de autorización.

**Dependencias separadas:** la integridad del snapshot documental y los 17 SKIP de aceptación deben resolverse por sus propietarios. Una modificación fusionada en una rama que no alcanza al `main` visible sigue **pendiente de entrega**.

## 7. Preguntas abiertas para revisores externos

- ¿Cuál es el menor mecanismo de fencing que protege una escritura **en el receptor**, no solo durante su preparación?
- ¿Qué prueba muestra que un inventario paginado sigue siendo completo bajo cambio de permisos y tiempo?
- ¿Cómo vincular iniciador, autorización, sesión y recibo sin incluir secretos en un journal?
- ¿Qué oráculo comprueba que el juez disiente del constructor cuando corresponde?
- ¿Cómo medir atención humana activa sin equipararla a latencia de respuesta?
- ¿Cómo validar la equivalencia de pantalla, voz y API con lectores reales?
- ¿Cómo prevenir que un merge a una rama intermedia aparezca como entregado en `main`?

## 8. Seguridad, procedencia y condiciones

Este resumen **no publica fixtures privados, estados de grants, nombres de máquinas, logs crudos, rutas sensibles ni recetas de explotación del sistema particular**. Los hallazgos se describen como categorías de riesgo y pruebas conceptuales, sin declarar incidentes productivos.

Los documentos públicos `RESEARCH-AGENDA.md`, `EXTERNAL-REFERENCES.md`, `MANIFEST-TEMPLATE.md` y la retrospectiva conservan su propia fecha y significado. La decisión para cambiar sistemas privados se toma aparte y queda en poder del Soberano. Las métricas que aún no cuentan con baseline se declaran `NO_DATA(not_measured)`.

**Síntesis:** hay coordinación conversacional reproducible y fallos concretos que orientar, pero no acreditación de ejecución autónoma completa. La prioridad es la **integridad de permisos, escritura, evidencia y accesibilidad** antes de ampliar el enjambre.
