# Agenda de investigación · SWARM (26-11-2026)

Documento público, conceptual y saneado. **No es una comisión ni un permiso de ejecución.** Cada propuesta requiere comparación con código existente, prueba y juicio independiente antes de cualquier cambio privado.

## Qué se ha observado y qué falta

| Eje | Existe / se reutiliza | Hueco verificable | Pregunta para investigación |
|---|---|---|---|
| Recuperación | CAMALEÓN, recibos, contratos de continuidad | Recuperar contexto no acredita sesión/GOAL ni capacidad de enviar | ¿Cómo recuperar tareas sin suplantación ni nuevas autoridades? |
| Inventario | MCP nativo y adaptador existentes | Respuestas de sesiones/GOAL excedían límites; PR de paginación pendiente de integración | ¿Cómo probar completitud y revocación entre páginas? |
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
