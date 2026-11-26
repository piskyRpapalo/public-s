# Retrospectiva SWARM · 25 noviembre 21:00 → 26 noviembre mañana (Europe/Lisbon)

**Objeto:** separar intención del Soberano, interpretación de orquestadores y resultado acreditado. Documento de estudio público, saneado, sin datos de sesiones, hosts, credenciales ni instrucciones operativas. No constituye una nueva comisión.

**Límite de reconstrucción:** las intenciones proceden de conversaciones y órdenes históricas; los resultados se contrastaron con documentos SWARM y recibos de Mesa #63. No existe aquí una transcripción completa minuto a minuto del periodo: `NO_DATA(complete_chronological_transcript_not_available)`. Las franjas son aproximadas y los hitos no deben interpretarse como mediciones de duración.

## 1. Tres perspectivas, por fases

| Franja aproximada | Qué quiso conseguir el Soberano | Qué entendieron los orquestadores | Qué se consiguió / qué no |
|---|---|---|---|
| 25 nov, desde 21:00 | Crear una colonia SWARM de agentes especializados que cooperen sin perder soberanía ni duplicar trabajo | Arquitectura de roles, contratos, Mesa, CLAIM, permisos, recibos y juez independiente | Contratos y piezas de roster, parser, scheduler y proyecciones; **NO_DATA** de activación real automática de agentes |
| 25 nov, noche | Un panel de bucle de agentes que permita observar trabajo y decidir el siguiente paso | SWARM como maqueta de coordinación, LAB como evidencia y APP/SuperBot como proyección de lectura | UI/contratos y pruebas sintéticas; el bucle completo de ejecución→verificación→visualización **no quedó acreditado** |
| 25 nov, noche tardía | Que cada agente trabaje de verdad, entregue pruebas y no anuncie resultados ficticios | Separación ACK/RESULT/COMPLETED_VERIFIED; constructor ≠ juez; pruebas adversariales | PR de unicidad CLAIM, recibos y controles; gate global aún con SKIP de aceptación |
| 26 nov, madrugada | Maximizar continuidad, trabajo útil y eficiencia; no volver a empezar al cambiar de conversación | R5 para recuperación, oportunidades, MCP, gobierno y EDGE; R6 solo planificar APP personalizada | R5 activada; R6/R7 condicionadas; no se acreditó cierre completo R5 |
| 26 nov, madrugada | CAMALEÓN para recuperar temporalmente contexto y continuar unidades autorizadas | READ_CONTEXT reversible y CONTINUE_UNIT con GOAL, CLAIM y turno escritor separados | Documentación, lanzadores y recibos; recuperación documental acreditada; ejecución CLI ajena **HOLD** sin IDs/grants verificables |
| 26 nov, antes del despertar | APP privada del Beelink con Hexelion conversacional, SuperBot, estados claros, colonia observable y voz accesible | Diferenciar servicio disponible, modelo cargado, chat que responde, autorización y experiencia física E2E | Código APP y pruebas CI avanzaron; MCP/PWA/chat observados; arnés 6/7 y turno de chat sin respuesta en 90 s; voz E2E **NO_DATA** |
| 26 nov, mañana | Operar desde el móvil sin intervención física rutinaria; recuperar capacidades remotas existentes antes de pedir comandos | Preflight MCP/SentinelX, identidad efectiva, alternativas remotas y diagnóstico acotado | Se identificó fallo de inventarios sobredimensionados y permisos de diagnóstico; la solución paginada se construyó en PR aislada, sin despliegue |
| 26 nov, mañana | Reconciliar resultados de NEXO, E y D; iniciar D/B/C y estudiar arquitectura externamente | NEXO coordina, E construye transporte, D juzga, B corrige testigo LAB, C reconcilia contratos | Recibos NEXO/E/D; E 24 fixtures PASS ×2 y PR draft; D R5 HOLD; B/C nuevas unidades pendientes de resultados |
| 26 nov, mañana | Separar investigación pública de decisiones y código privados | public-s como mesa de estudio; manifiesto futuro para SWARM privado | PR pública inicial integrada; agenda de investigación propuesta en PR separada; no se autorizó implementar el manifiesto |

## 2. Diferencia entre visión y entrega

**Visión:** el Soberano conversa desde el móvil; ChatGPT interpreta y coordina; MCP transporta acciones permitidas; Hexelion ejecuta dentro de su autoridad; SWARM organiza roles y continuidad; LAB conserva pruebas; un juez independiente decide validez técnica; APP/Acho muestran el mismo estado por voz, pantalla y máquina.

**Entregado como código/documentación:** roles, prompts, contratos, parser de intención, roster, scheduler de fixtures, proyecciones, grafo, CAMALEÓN documental, controles adversariales, mejoras de APP y prototipo de inventario MCP paginado.

**Observado como servicio:** MCP, chat y proyección APP estuvieron accesibles en cortes concretos. Esto no equivale a ciclo completo ni a que todos los preceptores estén activos.

**No acreditado E2E:** despertar arbitrariamente conversaciones Web; identificar de forma completa sesiones/GOAL a través del MCP activo; autorización por voz revocable con recuperación real; Hexelion respondiendo de forma fiable en APP; recepción y juicio automáticos de una unidad útil; voz física accesible con equivalencia de datos.

## 3. Fallos y desviaciones de interpretación

1. **Confundir actividad con progreso:** mensajes, sesiones, PR y CI parcial no son unidades útiles verificadas. Propuesta: medir resultados consumibles por Hexelion y tiempo de atención humana.
2. **Confundir maqueta con operación:** panel, roles y proyecciones no prueban agentes LIVE. Propuesta: mostrar estado/fuente/hora/cause sin inventar conectividad.
3. **Confundir continuidad de contexto con control de sesión:** CAMALEÓN READ_CONTEXT no transfiere grants. Propuesta: gates explícitos para CONTINUE_UNIT.
4. **Inventario MCP incompleto:** respuestas de sesiones y GOAL sobrepasaban el presupuesto; una implementación también recortaba listados sin indicar completitud. Propuesta: filtro y cursor con pruebas de ACL/revocación.
5. **CI rojo con trabajo parcial válido:** en cortes históricos, 17 SKIP de adapter ausente impedían el gate aunque las pruebas unitarias pasaran. Propuesta: distinguir fixture, integración y aceptación real.
6. **Diagnóstico remoto insuficiente:** se pidió intervención física antes de agotar herramientas existentes; permisos de usuario remoto y propietario del servicio no coincidían. Propuesta: preflight de identidad y capacidades antes de escalar.
7. **Chat local sin respuesta:** arnés observó 6/7 checks, con chat fallando tras 90 s. No atribuir causa a un modelo o endpoint sin aislarla; no restaurar alias retirados.
8. **Documentación desfasada:** comisión histórica y snapshots pueden describir menos roles o rondas anteriores. Propuesta: fuente canónica versionada y reconciliación sin borrar historia.

## 4. Qué aprendimos sobre el diseño

- **El bucle no es un panel decorativo:** debe correlacionar objetivo, agente, CLAIM, sesión, autorización, resultado, recibo, juez y siguiente unidad.
- **SWARM no es una segunda autoridad:** reutiliza MCP, APP, LAB y scheduler existentes. El Soberano conserva decisiones reservadas.
- **Hexelion debe entender evidencia, no relatos:** diferenciar PROPOSED, IMPLEMENTED, CONNECTED, WORKING y COMPLETED_VERIFIED.
- **Accesibilidad es un contrato de datos:** Acho debe expresar el mismo estado/cause/source/observed_at en pantalla, voz y API.
- **R5 antes de R6/R7:** primero continuidad, inventario, testigo y juez; después personalización APP y experimentos.
- **Publicación de estudio ≠ permiso de producción:** propuestas externas pasan por manifiesto, comparación, pruebas, decisión soberana y PR privada independiente.

## 5. Siguientes preguntas para el estudio público

1. ¿Qué evento inicia cada vuelta del bucle y qué condición la termina?
2. ¿Cuál es el registro canónico de estado: CLAIM, GOAL, journal o una proyección derivada?
3. ¿Cómo detectar trabajo duplicado entre chats y CLIs sin una base de datos adicional?
4. ¿Cómo auditar resultados sin que el constructor se autocertifique?
5. ¿Cómo comprobar que un inventario paginado no pierde filas cuando cambian permisos?
6. ¿Cómo representar incertidumbre y fallos en la APP sin saturarla de paneles?
7. ¿Cómo medir mejora en continuidad, calidad, energía y atención humana con baselines reproducibles?
8. ¿Qué parte de un proyecto externo se puede adaptar como algoritmo o prueba sin añadir otro servicio?

## 6. Fuentes canónicas para revisión privada

- SWARM: `PROMPTS.md`, `docs/SWARM_CONTRACT.md`, `docs/R5-PREPARATION.md`, `docs/ACCEPTANCE.md` y comisión histórica.
- Mesa #63: recibos de NEXO, E, D y los agentes que sigan trabajando.
- PR relevantes: SWARM #42/#43/#44/#46, APP #437, p0x #144.

**Nota:** los enlaces a recursos privados no dan acceso a lectores externos. No se incluyen contenidos privados literales. Los estados aquí son cortes históricos, no indicadores LIVE.

## 7. Resultado de esta retrospectiva

**Logrado:** arquitectura y lenguaje compartidos, componentes de coordinación y pruebas, recuperación contextual, avances APP y solución candidata de paginación.  
**Parcial:** correlación durable, reconciliación documental, auditoría y operación remota.  
**Pendiente de demostrar:** ciclo SWARM completo, control por voz accesible, Hexelion conversacional fiable desde APP y productividad verificable de extremo a extremo.

El siguiente documento, tras estudiar repositorios externos, será un **manifiesto de deltas mínimos** para el SWARM privado, sujeto a decisión soberana.
