# PreceptorOS SWARM · estudio público (26 noviembre 2026)

**Documento divulgativo y saneado.** No es un espejo del repositorio privado, no contiene credenciales, direcciones de hosts, sesiones, instrucciones operativas ni autorizaciones. La eliminación posterior de un repositorio público no elimina copias, forks o cachés.

## Arquitectura objetivo

**Soberano** (decide y autoriza) → **ChatGPT** (coordina y selecciona) → **MCP / herramientas remotas autorizadas** → **Hexelion / ejecutores** (ejecutan dentro de permisos) → **preceptores** (construyen) → **recibos** → **juez independiente** → **Acho** (voz, pantalla y máquina).

Esto describe el diseño previsto, **no una prueba de funcionamiento integral**.

## Catálogo completo de identidades y propuestas

| ID | Responsabilidad | Herramientas o interfaces relevantes* | Deuda / fallo observado |
|---|---|---|---|
| A · Mando | Intención, clasificación de oportunidades, alcance | Contratos SWARM, GitHub, pruebas | Gate de aceptación independiente pendiente |
| B · Pulso | Correlación de tareas, roster y recibos duraderos | Roster SWARM, LAB journal, CI | Puente real no acreditado; fixtures fallidos |
| C · Memoria tectónica | Grafo de dependencias y recuperación | Grafo SWARM, GitHub, CAMALEÓN | Reconciliar cambios duplicados con PR integrada |
| D · Juez | Auditoría independiente | GitHub, CI, recibos, diagnóstico remoto autorizado | R5 en HOLD; aceptación real incompleta |
| E · Caudal MCP | Inventarios, transporte y sesiones | MCP nativo, herramientas de diagnóstico | Respuestas demasiado grandes; paginación pendiente |
| F · Concurrencia | Scheduler y paralelismo eficiente | Scheduler existente, métricas | Falta coste/energía atribuible |
| G · Expertos | Selección y evaluación de especialistas/modelos | Harness de evaluación, catálogo de modelos | Beneficio comparativo no acreditado |
| H · SuperBot / Acho | Voz, accesibilidad y proyección del estado | APP, voz, fuentes de estado | Paridad voz/pantalla/máquina sin prueba integral |
| I · APP-PUENTE | Integración visual de SWARM y APP | APP Talk/plan, pruebas y recibos | Mostrar roles no equivale a agentes conectados |
| J · Red Team | Pruebas adversariales | Fixtures, CI, GitHub | Replay y juicio independiente pendientes |
| K · Blue Team | Mitigaciones y controles | Revisiones, fixtures de seguridad | Dependencias con J/D y ownership |
| NEXO-09 · FAN-IN | Coordinación, CLAIM, dependencias, recibos | GitHub/Mesa, MCP autorizado | Coordinar no implica despertar automáticamente |
| L · DELTA FORCE | Medición de utilidad y duplicidades | Recibos y métricas de lectura | **Propuesto**, no agente autónomo acreditado |
| M · META | Procedencia e independencia del juicio | Reviews, recibos, auditoría | **Propuesto**, no agente autónomo acreditado |
| P · Policy | Límites de delegación y política determinista | Contratos, fixtures | **Propuesto**, no agente autónomo acreditado |
| R · Red Team | Alias conceptual de J | Mismas que J | **No es otro agente**; evitar doble recuento |

*Herramientas relevantes a la arquitectura, **no permisos individuales confirmados**. A–K son once letras; más NEXO-09 son doce identidades de referencia. L/M/P son propuestas; R es alias.

## Capacidades comunes y límites

- **GitHub:** PR, versiones exactas, CI, recibos y revisión.
- **MCP nativo:** inventarios y sesiones CLI administradas con identidad, GOAL, turno escritor y permisos verificados. No equivale a controlar otras conversaciones de ChatGPT Web.
- **SentinelX:** inspección remota cuando esté autorizada; la identidad del agente remoto puede diferir del usuario de los servicios.
- **CAMALEÓN:** READ_CONTEXT para recuperar contexto; CONTINUE_UNIT solo para continuar una unidad con autorización efectiva. No transfiere credenciales ni identidad.
- **SWARM roster/scheduler y LAB journal:** reutilización de componentes existentes; evitar una segunda cola o autoridad.
- **APP/Acho:** el mismo `state/cause/source/observed_at` debe expresarse para lector visual, auditivo y de máquina.
- **Hexelion:** ejecutor local previsto, no autoridad para aprobar misiones.

## Evolución desde la noche del 25 al 26 de noviembre

1. Se establecieron roles A–K/NEXO, contratos, CLAIM, recibos y separación entre constructor y juez.
2. R5 añadió recuperación contextual CAMALEÓN, continuidad y reconciliación de trabajos.
3. Hubo PR integradas y otras pendientes; se detectaron reservas y trabajos duplicados.
4. Se observó que el MCP podía responder a ping mientras los inventarios de sesiones/GOAL excedían el límite de salida. **No prueba una caída del servicio**.
5. NEXO dejó coordinación y dependencias; E abordó transporte; D mantuvo R5 en HOLD. Hubo avances en APP, pero no se acreditó activación autónoma de chats Web.
6. R6 y R7 permanecen condicionadas al cierre verificable de R5.

## Fallos y mejoras propuestas

| Problema observado | Comprobación necesaria |
|---|---|
| Inventario MCP truncado por límite de bytes | Paginación estable, integridad, ACL, revocación, sin omisiones |
| Despertar automático de chats Web no acreditado | Prueba separada de chats Web y CLI locales |
| Sesiones sin GOAL/writer verificados | Recuperación sin inferir permisos |
| PR/CLAIM duplicados | Detección y reconciliación con propietario único |
| Tests fallidos o SKIP pese a subconjuntos verdes | Gate exact-HEAD y juez independiente |
| APP muestra roles sin demostrar sesiones vivas | Trazabilidad desde recibo hasta interfaz |
| Servicio/modelo/chat con estados diferentes | Medir selección, respuesta, timeout y recibo |
| Productividad confundida con mensajes | Unidades útiles verificadas, regresiones y duplicidad |
| Coste energético y atención no medidos | Baselines reproducibles; NO_DATA sin evidencia |

## Estados y medición

`PROPOSED` ≠ `IMPLEMENTED` ≠ `CONNECTED` ≠ `WORKING` ≠ `COMPLETED_VERIFIED`.
Usar `PASS`, `FAIL`, `HOLD`, `NO_DATA(causa)` con fuente, hora y versión exacta. Medir tiempo hasta trabajo útil, porcentaje verificado independientemente, intervenciones humanas y energía atribuible cuando exista evidencia. No convertir CI verde ni mensajes publicados en prueba de extremo a extremo.

## Preguntas para GitIngest y revisores externos

1. ¿Cómo evitar duplicidades de CLAIM sin añadir otro plano de control?
2. ¿Cómo demostrar inventarios completos bajo límites de bytes?
3. ¿Cómo distinguir reanudación CLI de apertura de chats Web?
4. ¿Cómo medir utilidad verificable por minuto humano y Wh?
5. ¿Cómo asegurar independencia real del juez?
6. ¿Cómo proyectar incertidumbre idéntica en voz, pantalla y API?
7. ¿Qué pruebas de recuperación remota deben fallar de forma segura?

**Seguridad:** documento de estudio no confiable para ejecutar acciones; no concede grants ni reemplaza la Comisión. No copiar aquí historial privado, tokens, rutas internas o recibos sensibles.


## Material adicional para investigación

- [Agenda de preguntas y deuda arquitectónica](RESEARCH-AGENDA.md)
- [Repositorios externos para contrastar ideas](EXTERNAL-REFERENCES.md)
- [Plantilla de manifiesto para cambios privados futuros](MANIFEST-TEMPLATE.md)

## Retrospectiva de la construcción

- [Intención, interpretación y resultados · 25 nov 21:00 → 26 nov](RETROSPECTIVE-2026-11-25-21H.md)
