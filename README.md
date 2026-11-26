# PreceptorOS SWARM · estudio público (26 noviembre 2026)

**Documento divulgativo y saneado.** No es un espejo del repositorio privado, no contiene credenciales, direcciones de hosts, sesiones, instrucciones operativas ni autorizaciones. La eliminación posterior de un repositorio público no elimina copias, forks o cachés.

## Ideas26nov · Parte 3 y Adenda A3 contrastadas

**[Síntesis de la Parte 3/3, Adenda A3 y diferencias con el sistema existente](IDEAS26NOV-V03-PARTE3-SINTESIS-PUBLICA-2026-11-26.md)**. Recupera los patrones U7 MCP Tasks, U8 evolución revisada, U9 aislamiento/ARIA y U10 CAMALEÓN propuesto, además de cinco líneas defensivas A3 y la skill `o.secret_detection` que faltaba en el resumen de Parte 2. **No se ha sustituido el contrato CAMALEÓN ni instalado un servicio.**

**Dos documentos complementarios preparan la Ronda 4:** la [guía de recepción y reconciliación](PREPARACION-IDEAS26NOV-RONDA4-2026-11-26.md) y el [estudio visual, CineK y continuidad del ecosistema](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md). S · VISION y T · MOTION son candidatos documentales; L · DELTA FORCE conserva su contrato de utilidad. `NO_DATA(source_round4_U11_U14_text_not_received)` hasta que llegue el texto real.

## Preparación de Ideas26nov · Ronda 4

**[Traspaso Ronda 4: recuperación visual, CineK y continuidad del ecosistema](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md).** Las **Partes 1, 2 y 3** de Ideas26nov ya están recibidas a nivel documental; la **Parte 4 y los contratos U11–U14** todavía no han sido aportados. El documento prepara el siguiente texto para el autor, sin pretender que esté aprobado, instalado o fusionado con los contratos privados.

**Ground truth recuperado:** el inventario GitHub contiene **22 repositorios (21 no archivados y 1 archivado)**; doce fichas de dominio A–K + NEXO-09 fueron incorporadas al `main` del SWARM por PR #52–#63. **Son skills propuestas, no doce funciones E2E acreditadas.** La reconciliación CAMALEÓN v0.3 sigue en una PR documental independiente; conserva la ruta Web→CLI local **condicionada a permisos reales**, que la propuesta externa denegaba indiscriminadamente. R5 cerrado administrativamente, aceptación técnica HOLD; R6 PLAN ONLY y R7 no activada.

**Visual y cine:** S · VISION y T · MOTION son identidades **candidatas**; L · DELTA FORCE ya tiene un contrato de evaluación de utilidad que no debe reemplazarse. CineK conserva gobierno independiente y requisitos explícitos para el panel APP y una eventual convergencia. Ningún render actual, instalación ni lanzamiento de S/T queda acreditado por el estudio. Las 50/30/20 cuotas de productos/deuda/harness son una **hipótesis**, no una medición.

### Traspaso histórico para Parte 3

La [guía anterior para redactar la Parte 3](PREPARACION-IDEAS26NOV-PARTE3-2026-11-26.md) queda como documento **histórico** de un corte en el que aún no se había recibido. Ya no representa el estado actual. No la utilices como autorización para CAMALEÓN v0.3.

## Ideas26nov v0.3 · Parte 2 recibida

Ya está disponible la **[síntesis de la Parte 2: N · VIGÍA, O · ADUANA, REGISTRO-DE-VIGÍA y deltas U0–U10](IDEAS26NOV-V03-PARTE2-N-O-U0-U10.md)**. Aporta contratos de exploración de fuentes, cuarentena, adopción con revisión y nuevas propuestas sobre MCP Tasks, evolución con gates y navegador aislado. **N/O permanecen PROPOSED**, sin ejecución, privilegios, grants o nueva autoridad. Se resuelve la ausencia de su definición documental; la ejecución E2E sigue NO_DATA. La Parte 3/3 ya fue recibida y contrastada en la síntesis pública enlazada al inicio; no se adopta sin revisión.

## PRE-R6 · doce dominios en evolución documental

**[MVP nativo y skills de los doce dominios](MVP-NATIVO-SKILLS-12-DOMINIOS-2026-11-26.md)** · Contratos de propuesta para A–K y NEXO-09, con reutilización de herramientas existentes, pruebas adversariales, dueño, métricas, evidencia y reversión. Es una **ronda de investigación paralela**, no doce CLI activos ni doce servicios desplegados.

**Estado de gobierno actualizado:** `R5_WORK_CYCLE=CLOSED_ADMINISTRATIVELY_BY_SOVEREIGN`; `R5_TECHNICAL_ACCEPTANCE=HOLD` (fallos y datos pendientes siguen bloqueados); `R6=PLAN_ONLY`; `R7=NOT_ACTIVATED`. El cierre administrativo no rebaja seguridad ni constituye firma criptográfica. Los contratos documentales N/O y los deltas U0–U10 ya tienen fuente en Ideas26nov Parte 2; la Parte 3 ya tiene fuente, pero las pruebas de ejecución siguen `NO_DATA(e2e_unverified)`.

## Estudio prioritario: capacidades de agentes y mejora de MCP

- **[Capacidades agentic, MCP y experimentos reproducibles · 26 nov 2026](AGENT-CAPABILITIES-MCP-2026-11-26.md)**. Documento principal para revisar qué aportan los roles, qué reutilizar del MCP existente, cómo evitar escritor obsoleto, inventarios falsamente completos y resultados no verificados; incluye StrongDM, P1–P7, métricas, riesgos y pruebas adversariales. **Estudio público, no acreditación LIVE ni autorización de integración privada.**

## Actualización de continuidad · segunda mitad de la mañana del 26/11/2026

El estudio incluye ahora **[StrongDM + P1–P7 y la continuidad de seis carriles](CONTINUIDAD-AGENTIC-SWARM-2026-11-26.md)**. Se recuperaron seis unidades conversacionales con asignación determinista y recibos; **no** queda acreditado que seis procesos CLI se hayan iniciado ni que exista ya un bucle autónomo E2E.

**Resultado de las rondas:** el inventario MCP dispone de código de paginación y correcciones probadas en fixtures, pero el esquema del servicio efectivamente conectado sigue sin acreditar completitud; el juez detectó problemas adicionales de vigencia temporal; hay carreras de escritor tardío sin fencing en el punto de efecto; el consumidor accesible identificó respuestas incompatibles con filtros/presupuestos; también apareció una diferencia entre una PR marcada como fusionada y los archivos realmente presentes en `main`. Los gates de aceptación permanecen pendientes.

**Decisión de investigación:** KEEP del patrón StrongDM (atribución y autorización por acción), HOLD del producto propietario; KEEP de ideas P1–P7, sin nuevos servicios, grants, despliegue ni dependencias automáticas. **R5 cerrado administrativamente; aceptación técnica HOLD; R6 PLAN ONLY condicionado; R7 no activada.** Los estados son cortes documentales y no telemetría en directo.

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
| E · Caudal MCP | Inventarios, transporte y sesiones | MCP nativo, herramientas de diagnóstico | Paginación construida y probada en fixtures; servicio conectado y vigencia temporal sin acreditar completamente |
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

- [Síntesis Parte 3 y Adenda A3 contrastadas](IDEAS26NOV-V03-PARTE3-SINTESIS-PUBLICA-2026-11-26.md)
- [Ronda 4 · traspaso general de ground truth](PREPARACION-IDEAS26NOV-RONDA4-2026-11-26.md)
- [Ronda 4 · visión, CineK y continuidad de productos](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md)

- [Preparación de Ideas26nov Ronda 4 · visión, CineK y continuidad del ecosistema](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md)

- [Traspaso para redactar Ideas26nov Parte 3/3](PREPARACION-IDEAS26NOV-PARTE3-2026-11-26.md)
- [Ideas26nov Parte 2/3 · N/O y deltas U0–U10](IDEAS26NOV-V03-PARTE2-N-O-U0-U10.md)

- [Doce dominios: MVP nativos, skills propuestas y pruebas](MVP-NATIVO-SKILLS-12-DOMINIOS-2026-11-26.md)

- [StrongDM, P1–P7 y aprendizajes de seis carriles paralelos (26 nov)](CONTINUIDAD-AGENTIC-SWARM-2026-11-26.md)

- [Agenda de preguntas y deuda arquitectónica](RESEARCH-AGENDA.md)
- [Repositorios externos para contrastar ideas](EXTERNAL-REFERENCES.md)
- [Plantilla de manifiesto para cambios privados futuros](MANIFEST-TEMPLATE.md)

## Retrospectiva de la construcción

- [Intención, interpretación y resultados · 25 nov 21:00 → 26 nov](RETROSPECTIVE-2026-11-25-21H.md)
