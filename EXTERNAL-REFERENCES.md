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
