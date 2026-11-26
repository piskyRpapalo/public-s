# Referencias externas para contraste, no recomendaciones de sustitución

Enlaces a repositorios públicos conocidos. **NO_DATA(revisión comparativa actual no ejecutada):** esta lista no afirma que su código sea superior ni que sus licencias, APIs o actividad actual estén verificadas hoy. Investigar versiones, licencia, mantenimiento y pruebas antes de adoptar.

| Proyecto | URL | Aspecto a estudiar | Riesgo de adaptación |
|---|---|---|---|
| Temporal | https://github.com/temporalio/temporal | Workflows duraderos, reintentos, historial | Puede duplicar scheduler/servicios existentes |
| LangGraph | https://github.com/langchain-ai/langgraph | Estado de agentes, checkpoints y recuperación | Dependencias y nuevo plano de control |
| AutoGen | https://github.com/microsoft/autogen | Mensajería y coordinación multiagente | Abstracción excesiva frente a MCP nativo |
| OpenHands | https://github.com/All-Hands-AI/OpenHands | Ejecución de tareas de software y evaluación | Aislamiento y privilegios de herramientas |
| OpenTelemetry | https://github.com/open-telemetry/opentelemetry-specification | Trazas, métricas y procedencia | Cardinalidad, privacidad y sobrecarga |
| Open Policy Agent | https://github.com/open-policy-agent/opa | Políticas explícitas y pruebas de denegación | No crear autoridad paralela |
| Cedar | https://github.com/cedar-policy/cedar | Autorización declarativa verificable | Semántica distinta de grants existentes |
| Model Context Protocol | https://github.com/modelcontextprotocol/specification | Contratos de transporte y herramientas | Compatibilidad con adaptador ya desplegado |
| pytest | https://github.com/pytest-dev/pytest | Fixtures, parametrización, reproducción | No confundir tests de fixture con E2E |
| W3C ARIA APG | https://github.com/w3c/aria-practices | Patrones accesibles de UI | Validación con lectores reales pendiente |

## Referencias incorporadas en el estudio StrongDM + P1–P7 (26NOV2026)

Son referencias **para contraste**, no productos usados ni dependencias recomendadas. Antes de reutilizar código o catálogos se deben comprobar commit/tag, LICENSE y dependencias concretas; las licencias no quedan certificadas por esta tabla.

| Referencia | Enlace público | Pregunta de investigación | Decisión provisional |
|---|---|---|---|
| StrongDM Secure AI / MCP / Attribution | https://docs.strongdm.com/ai | Política por acción, iniciador, separación de credenciales y trazas; **broker propietario no auditable aquí** | KEEP patrón; HOLD producto |
| Kubernetes API pagination | https://kubernetes.io/docs/reference/using-api/api-concepts/ | Cursor, consistencia y expiración de snapshot sin falsas completitudes | KEEP semántica |
| Fencing / etcd | https://etcd.io/docs/ | Tokens monótonos comprobados en el **receptor del efecto** | KEEP patrón |
| ai-agent-detect | https://github.com/agent-detect/ai-agent-detect | Evidencia de iniciador CLI/Web; riesgo de confiar en variables heredadas | KEEP concepto; HOLD copia de catálogo/licencia |
| CodeCarbon | https://github.com/mlco2/codecarbon | Wh local medido frente a estimaciones TDP | KEEP metodología; HOLD integración |
| EcoLogits | https://github.com/mlco2/ecologits | Energía remota estimada con incertidumbre explícita | KEEP metodología; HOLD integración |
| Evaluación de jueces | https://arxiv.org/ | Normalización, evaluación ciega y sensibilidad al estilo; **NO_DATA(paper_exact_version_not_verified)** | KEEP pregunta y fixtures, no dependencia |
| MDN ARIA Live Regions | https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Guides/Live_regions | Región persistente, severidad de anuncios y accesibilidad real | KEEP reglas |
| LitmusChaos | https://github.com/litmuschaos/litmus | Inyección verificada, retorno al estado estacionario y rollback | KEEP método; HOLD operador |
| Chaos Mesh | https://github.com/chaos-mesh/chaos-mesh | Blast radius, reversión y aborto en experimentos | KEEP método; HOLD operador |

Más detalles y pruebas adversariales: [Continuidad agentic y seis carriles](CONTINUIDAD-AGENTIC-SWARM-2026-11-26.md).

## Plantilla de comparación

**Problema:** ¿qué fallo concreto resuelve?  
**Base actual:** ¿qué archivo, interfaz o prueba existente lo aborda?  
**Referencia:** commit/tag, licencia, prueba o benchmark externo.  
**Diferencia:** ¿qué falta en el sistema actual?  
**Adaptación mínima:** ¿qué contrato existente se extiende?  
**Prueba:** fixture + integración + adversarial + accesibilidad cuando aplique.  
**Coste:** tiempo, memoria, energía, atención humana y mantenimiento, si medibles.  
**Riesgo:** autoridad, privacidad, dependencias, duplicación y regresiones.  
**Decisión:** KEEP / HOLD / DISCARD, con causa y responsable.

No incorporar dependencias automáticamente; primero evaluar conceptos y pruebas reproducibles.

## Capacidades de agentes, gobierno del MCP y continuidad · ampliación 26 noviembre

Estas fuentes son **referencias para estudiar patrones**, no prueba de rendimiento, licencia exacta o necesidad de instalar un producto. En particular, la solución empresarial de StrongDM/Delinea no es software abierto; no se propone adoptar su servicio o broker.

| Referencia | Enlace | Patrón que merece contraste | Evidencia local necesaria antes de adoptar |
|---|---|---|---|
| StrongDM Secure AI / Attribution | https://docs.strongdm.com/ai | Autorización por acción, identidad de iniciador y traza de denegación | Verificar principal y scope efectivo sin otro broker |
| Kubernetes API list/continue | https://kubernetes.io/docs/reference/using-api/api-concepts/ | Cursor, snapshot, caducidad, respuesta explícita | Filas completas bajo concurrencia, límite y revocación |
| etcd | https://github.com/etcd-io/etcd | Revisión monótona / exclusión con fencing | Receptor rechaza escritor antiguo; sin nueva DB por defecto |
| CodeCarbon | https://github.com/mlco2/codecarbon | Medición local o estimación energética identificada | Método, resolución, atribución y revisión de versión/licencia |
| EcoLogits | https://github.com/mlco2/ecologits | Estimación remota con incertidumbre | Rango/método separado de Wh medidos y revisión de dependencias |
| W3C WCAG 4.1.3 | https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html | Anuncios de estados de forma accesible | Pruebas semánticas + lector físico real |
| LitmusChaos | https://github.com/litmuschaos/litmus | Steady state, inyección verificada, abort y reversión | Fixture aislado, sin instalar operador por defecto |

**Documento de aplicación:** [capacidades y evolución MCP](AGENT-CAPABILITIES-MCP-2026-11-26.md). **NO_DATA(revisión_completa_de_licencias_y_versiones)** para integración de dependencias ajenas; estudiar algoritmos antes que servicios.

## Inspiraciones para MVP nativos de doce dominios (PRE-R6)

**No es un inventario de software instalado.** Las referencias siguientes proceden de investigación conceptual y requieren verificar la licencia, el tag y las dependencias exactas antes de reutilizar código. El estudio de dominios se encuentra en [MVP nativo y skills](MVP-NATIVO-SKILLS-12-DOMINIOS-2026-11-26.md).

| Proyecto | Referencia | Patrón estudiado | Adaptación mínima / límite |
|---|---|---|---|
| celld | https://github.com/denoland/celld | Actor nominal y serialización en el receptor | Reutilizar el sink existente; no adoptar daemon adicional. Licencia exacta NO_DATA. |
| OpenCode | https://github.com/anomalyco/opencode | Denegación por defecto antes de acción consecuencial | Política dentro del adaptador actual, no un segundo control. Revisión licencia/versión pendiente. |
| Hermes Agent | https://github.com/NousResearch/hermes-agent | Curator de skills, pin/lock, delegación por presupuesto, coste y procedencia | Skills propuestas bajo revisión, sin ejecutar marketplace ni auto-mejora no juzgada. |
| Orca | https://github.com/stablyai/orca | Trabajo paralelo aislado por worktrees y Git como testigo | Un dueño por unidad y entrega verificada en destino exacto; no DB nueva. Licencia NO_DATA. |
| W3C ARIA live regions | https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Guides/Live_regions | Estado programáticamente anunciable | Región persistente, avisos por criticidad, lector físico independiente de fixtures. |

**Material defensivo de forks retirados:** no clonar ni ejecutar códigos o cargas asociadas a iniciativas ofensivas que carezcan de origen auditado. Usar únicamente casos sintéticos y revisión de seguridad para J/K. **Corte histórico:** esta sección se escribió antes de recibir las Partes 2 y 3. **Ahora ambas se han leído documentalmente**; sus propuestas no están aprobadas ni instaladas. Para la Parte 4 y los U11–U14 anunciados en A3, `NO_DATA(source_not_received)`.

## Ronda 4 · patrones visuales y continuidad que deben estudiarse, no instalarse

**[Guía de preparación Ronda 4](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md)**. Antes de probar una dependencia externa, confirmar licencia/tag/commit/permiso y comprobar si APP/WEB/CineK/TextCAD ya resuelven el problema. No presentar el catálogo como inventario de software instalado.

| Referencia o producto | Fuente pública | Reutilización conceptual | Gate |
|---|---|---|---|
| APP y WEB | https://github.com/piskyRpapalo/preceptoros-app y https://github.com/piskyRpapalo/preceptoros-web | Capturas auténticas, versiones, demostraciones reproducibles y documentación accesible | Fuente/HEAD, testigo de funcionalidad, alt text; mock etiquetado |
| LAB / STUDY | https://github.com/piskyRpapalo/lab y https://github.com/piskyRpapalo/study | Fixtures de modelos, evaluación visual y difusión del conocimiento | No inferir rendimiento por README o ejemplo |
| TextCAD | https://github.com/piskyRpapalo/textcad | Referencia para render visual, validación y corrección | Revisar licencia/implementación en HEAD; no reconstruir |
| CineK (gobierno propio) | Nombre de proyecto, sin publicar rutas de gestión ni infraestructura | Estudio del pipeline cinematográfico histórico y transferencia eventual mediante interfaz acordada | Independencia contractual, permisos, derechos, estado actual NO_DATA |
| W3C WAI / WCAG | https://www.w3.org/WAI/standards-guidelines/wcag/ | Texto alternativo, subtítulos, navegación y semántica equivalente | Snapshot sintético no sustituye lector físico |
| SVG y Mermaid | https://www.w3.org/TR/SVG2/ y https://mermaid.js.org/ | Diagramas versionables, accesibles cuando se acompañan de texto | No inventar servicios ni flujos LIVE |

**Producción audiovisual sin dependencia nueva:** evento sintético → guion/storyboard → render solo tras autorizar el motor existente → subtítulos y verificación → publicación autorizada. S/T son nombres **propuestos**, L conserva el rol real de evaluación de utilidad. El plan de reparto 50/30/20 carece todavía de baseline.
