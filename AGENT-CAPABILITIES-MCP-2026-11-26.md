# SWARM · Capacidades agentic, MCP y pruebas de soberanía
## Estudio público para revisión externa · 26 noviembre 2026

**Naturaleza:** estudio arquitectónico saneado, no copia del SWARM privado ni comisión de ejecución. No se publican recibos internos, identificadores de sesiones, secretos, nombres de equipos, rutas operativas, políticas privadas ni instrucciones de acceso. **KEEP/HOLD/DISCARD son decisiones de investigación**, no permisos de despliegue.

**Objetivo:** mejorar cuántas **unidades útiles verificadas** producen los agentes por minuto de atención humana y por Wh, sin añadir por defecto otro orquestador, broker, scheduler, base de datos o aplicación.

## 1. La capacidad importa más que el número de agentes

Los estados son distintos: `PROPOSED ≠ IMPLEMENTED ≠ CONNECTED ≠ WORKING ≠ COMPLETED_VERIFIED`. Un prompt, PR fusionada, respuesta a ping o interfaz visible **no** prueban automáticamente que un agente trabaje y cierre una unidad E2E.

| Rol de referencia | Capacidad que debe aportar | Reutilización preferida | Puerta de evidencia |
|---|---|---|---|
| A · Mando | Interpretar intención y abstenerse ante ambigüedad | Parser y contrato de intención | Falso despacho autorizado = 0 en pruebas adversariales |
| B · Pulso | Correlación y unicidad de agente/GOAL/sesión/operación/recibo | Roster + journals APP/LAB | Replay duradero tras reinicio, revocación y carrera |
| C · Memoria | Recuperar unidades sin suplantar actor | Grafo, versiones, recibos, CAMALEÓN | Contexto recuperado ≠ autorización heredada |
| D · Juez | Auditar HEAD exacto independientemente | CI y runner de prueba aislado | Contraejemplo detectado aun con relato convincente |
| E · Caudal MCP | Inventarios completos y autorizados, transporte limitado | MCP nativo existente | Todas las páginas; sin omisiones ni falso COMPLETE |
| F · Concurrencia | Programar trabajo sin escritores duplicados | Scheduler/DAG existente | 0 efectos admitidos por writer obsoleto |
| G · Expertos | Evaluar modelos/especialistas con procedencia | Harness y catálogo actuales | Digest, licencia, baseline y juez |
| H · Acho | Paridad de incertidumbre visual/voz/máquina | Proyección APP y consumidor existentes | Igualdad semántica, más prueba física de accesibilidad |
| I · APP | Presentar y controlar el ciclo autorizado | APP, Talk, ledger y permisos actuales | Acción y revocación E2E sin falso LIVE |
| J · Red Team | Probar denegaciones y fallo seguro | Fixtures adversariales | Inyección realmente aplicada y fallo detectado |
| K · Blue Team | Contener y revertir sin ampliar privilegios | Controles y rollback actuales | Sondas de recuperación/abort reproducibles |
| NEXO-09 | Coordinar propietarios, CLAIM y FAN-IN | Mesa, PR, recibos | Cero duplicación de unidades, dependencias explícitas |
| L · DELTA FORCE | Medir utilidad, energía y atención | Recibos/telemetría existentes | Wh medido ≠ estimado; atención activa ≠ latencia |
| M · META | Medir independencia/sesgos del juez | Runner y revisión selectiva | Estabilidad, desacuerdos y muestra humana |
| P · Policy | Evaluar permisos por acción, sin concederlos | Gate del adaptador MCP | Falla cerrado ante principal desconocido |

**L, M y P son capacidades de diseño, no procesos acreditados.** R es alias conceptual de J. **Seis conversaciones simultáneas no son prueba de seis CLI vivos**; la única fuente de actividad ha de ser el testigo que observe la acción realmente ejecutada.

## 2. MCP · diferencias entre conexión, inventario y autoridad

### Capacidades existentes que deben reutilizarse

- Adaptador y transporte MCP con inventarios, funciones de consulta y pruebas sintéticas de paginación.
- Contratos de identidad, CLAIM, GOAL y turnos escritores, junto con journal y pruebas adversariales.
- Proyección APP/Acho y mecanismos de coordinación sin ampliar permisos desde texto.

**No acreditado en este estudio público:** versión exacta del servicio MCP servido, recorrido autorizado de todas las páginas, identidad remota autenticada, despacho de un writer recuperado, efecto remoto y recibo final unidos en una sola prueba E2E. `NO_DATA(no_public_end_to_end_evidence)`.

### Prioridades medibles del MCP

| Prioridad | Cambio mínimo a estudiar | Prueba adversarial | Medida |
|---|---|---|---|
| P0 · Completitud | Cursor ligado a versión/scope; respuesta `complete` y causa explícita al caducar | Revocación, alta/baja, error de registro durante paginación | 0 falsos completos; filas/total = 1 cuando haya oráculo |
| P0 · Writer exclusivo | CLAIM determinista, CAS real y fencing **comprobado en el punto de efecto**, no solo TTL | Dos writers; se pausa A, entra B, A vuelve a escribir | 0 efectos obsoletos y 0 dos dueños/1000 ensayos |
| P0 · Revocación temporal | Verificar cambios de lease/grant/GOAL hasta el punto final de autorización | Reloj cruza límite entre lectura y respuesta | No publicar permiso caducado |
| P1 · Atribución | `initiator` declarado separado de principal autenticado | Web declara ser CLI; variable heredada falsifica identidad | Falsos ALLOW = 0 |
| P1 · Compatibilidad | Negociación de protocolo y respuesta legacy completa o error | Cliente antiguo trata la primera página como todo | 0 truncamientos silenciosos |
| P1 · Integridad del consumidor | Validación de filtro, estado y presupuesto de bytes antes de aceptar una fila | Respuesta filtrada contiene registros ajenos o sobredimensionados | 0 falsos `complete` en fixtures |
| P1 · Testigo | Enlace entre acción, alcance vigente, efecto y recibo duradero | ACK sin efecto, sesión cambiada, replay de RESULT | 0 falsos `COMPLETED_VERIFIED` |
| P2 · Coste | Trazas locales sin secretos y medición de consumo atribuible | Concurrencia impide atribuir Wh a una unidad | `NO_DATA(cause)` honesto, sin energía inventada |

**Precauciones técnicas:** un token cursor opaco no demuestra snapshot atómico; un journal append-only no proporciona CAS automáticamente; un identificador monotónico no protege si el receptor no lo compara; un cambio de prompt no autentica una sesión CLI. Un error `INVENTORY_EXPIRED` es una **semántica propuesta** que debe adaptarse a los códigos reales, no una afirmación sobre el protocolo desplegado.

## 3. Recuperación CAMALEÓN sin confundir contexto y control

**READ_CONTEXT:** recuperar fuentes, decisión previa, propietarios, HEAD, pruebas y recibo. Se puede usar desde una conversación Web dentro de sus permisos reales.

**CONTINUE_UNIT documental:** continuar un trabajo con las herramientas y permisos que la sesión ejecutora **ya tiene**. No adquiere un writer CLI ajeno.

**Continuación de CLI con efectos:** exige principal, sesión, GOAL, turno, grant y alcance verificables y vigentes. Si no existe testigo verificable: `HOLD/NO_DATA(cause)`; nunca herencia por nombre, env o una respuesta del modelo.

La responsabilidad de **NEXO** es conciliar reservas cooperativas y dependencias. Los comentarios de coordinación no sustituyen exclusión atómica en el recurso receptor.

## 4. Patrón StrongDM y siete ideas de continuidad (solo investigación)

| Idea | Patrón externo para contrastar | Decisión provisional y límite |
|---|---|---|
| Autorización por llamada | StrongDM AI / Broker / Attribution | KEEP principio, HOLD producto propietario; no otro plano de control |
| P1 Duplicidad CLAIM | Temporal Workflow ID, etcd fencing | KEEP ID determinista + token verificado en sink; DISCARD otro scheduler |
| P2 Paginación consistente | Kubernetes list/continue/resourceVersion | KEEP semántica; no prometer snapshot cuando el almacén no lo garantiza |
| P3 Identidad CLI/Web | StrongDM Attribution, detección con niveles de evidencia | KEEP procedencia; verificar licencia de cualquier catálogo antes de copiar |
| P4 Energía y atención | CodeCarbon / EcoLogits, OpenTelemetry | KEEP medición/estimación etiquetadas; HOLD nuevas dependencias hasta revisión |
| P5 Juez independiente | Auditoría ciega, replay de runner distinto, sesgos | KEEP fixtures y calibración; no framework nuevo automático |
| P6 Accesibilidad | W3C ARIA, WCAG 4.1.3 | KEEP único estado semántico; lector físico separado del test sintético |
| P7 Resiliencia | Ingeniería del caos, LitmusChaos/Chaos Mesh | KEEP método en entorno aislado; HOLD operadores externos |

Fuentes: [StrongDM AI](https://docs.strongdm.com/ai), [Kubernetes API Concepts](https://kubernetes.io/docs/reference/using-api/api-concepts/), [Temporal](https://github.com/temporalio/temporal), [OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification), [CodeCarbon](https://github.com/mlco2/codecarbon), [EcoLogits](https://github.com/mlco2/ecologits), [W3C ARIA APG](https://github.com/w3c/aria-practices). **NO_DATA(external_code_version_license_review_not_executed_for_all_sources)**: no copiar código ni incorporar librerías sin comprobar versión, licencia y mantenimiento.

## 5. Experimentos de capacidades para la siguiente ronda de agentes

**Experimento A — doble writer + revocación:** dos actores solicitan la misma unidad; el primero se pausa, expira, otro continúa y el primero regresa. El receptor debe bloquear el efecto antiguo incluso si el cliente afirma tener el permiso. Registrar revisión/titular/efecto, latencia y falsos ALLOW. Exigir aislamiento y rollback.

**Experimento B — inventario MCP completo:** el oráculo conoce N registros autorizados; en paginación se inyectan revocación, alta, corrupción, caducidad y respuesta superior al presupuesto. Debe producir N registros coherentes o fallo explícito con causa, sin ocultar omisiones. Contar bytes UTF-8 incluyendo envolvente.

**Experimento C — recibo verificable:** una operación devuelve ACK y luego una respuesta sin testigo de efecto. Debe mantenerse `NO_DATA` o `HOLD`, no `COMPLETED_VERIFIED`. Repetir con reinicio y sesión migrada.

**Experimento D — CAMALEÓN Web/CLI:** una conversación Web intenta continuar el turno de una CLI. Debe poder leer el contexto permitido, pero no adoptar sesión/grant ajenos. Medir falsas escaladas y tiempo de recuperación.

**Experimento E — Acho en tres canales:** 100 transiciones con estados conocidos, revocados, parciales y desconocidos. Comparar `state/cause/source/observed_at/evidence_ref` semánticamente en visual, voz y salida máquina; probar voz física aparte con tecnología asistiva real y consentimiento.

**Experimento F — juez robusto:** HEAD defectuoso con relato convincente. El runner independiente debe encontrar el defecto y registrar estabilidad, tasa de falsos PASS y limitación de independencia cuando no hay un principal distinto.

**Experimento G — rendimiento útil:** contabilizar solo unidades verificadas por juez; separar Wh medidos de estimados y minutos de intervención activa de latencia. No asignar consumo compartido sin método reproducible.

**Regla de validación:** la inyección de un fallo debe quedar observada. Sin inyección, el experimento es `NO_DATA(injection_not_applied)`, jamás PASS.

## 6. Preguntas para revisión externa / GitIngest

1. ¿Qué módulo mínimo ofrece CAS linealizable y fencing al **receptor del efecto** sin crear otro almacenamiento?
2. ¿Cómo componer paginación, revocación y expiración sin fuga temporal ni falso inventario completo?
3. ¿Qué identidad puede acreditar un MCP conectado sin exponer secretos ni basarse en claims del cliente?
4. ¿Qué estructura compacta de recibo permite a otro juez reproducir el cierre de una unidad?
5. ¿Cómo evitar que la interfaz de seis agentes convierta una conversación existente en una sesión falsamente LIVE?
6. ¿Qué métricas reproducibles muestran que un nuevo contrato mejora utilidad/atención/Wh más que otra capa de agentes?
7. ¿Cómo mantener el mismo estado en Acho para lectores de pantalla y API sin duplicar anuncios?

## 7. Ficha pública de recomendación

Para cada mejora entregar **problema → fuente pública y licencia → capacidad ya existente → delta mínimo → benchmark/baseline → prueba adversarial → riesgo/rollback → KEEP/HOLD/DISCARD → próximo entregable**. En la propuesta privada posterior, añadir HEAD exacto, responsable y revisión de permisos por quien corresponda.

**Límites de publicación:** nunca subir dumps MCP, recibos privados, nombres de sesiones/GOAL, políticas de grants, datos de red, claves o trazas con identidades. La publicación permite revisión intelectual; **no es comisión, certificación E2E, ni permiso de ejecutar**.
