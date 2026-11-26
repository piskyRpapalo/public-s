# Plantilla de manifiesto de cambio · PROPUESTA, no autorización

```yaml
manifest_version: "proposal/1"
title: "CAMBIAR"
status: "PROPOSED"
owner_role: "CAMBIAR"
executor_identity: "NO_DATA(unassigned)"
source_private_reference: "NO_DATA(not_verified)"
baseline_commit: "NO_DATA(not_verified)"
problem: "CAMBIAR"
existing_components: []
proposed_delta: "CAMBIAR"
non_goals:
  - "No duplicar MCP, APP, scheduler, base de datos o autoridad"
  - "No ampliar grants por inferencia"
dependencies: []
external_references: []
license_review: "NO_DATA(not_reviewed)"
risks: []
rollback_plan: "CAMBIAR"
metrics:
  useful_verified_units: "NO_DATA(not_measured)"
  human_attention_minutes: "NO_DATA(not_measured)"
  energy_wh: "NO_DATA(not_measured)"
tests:
  deterministic: []
  adversarial: []
  integration: []
  accessibility: []
independent_judge: "PENDING"
sovereign_decision: "PENDING"
implementation_authorized: false
merge_authorized: false
deploy_authorized: false
```

## Puertas de decisión

1. Investigar y contrastar con código existente.
2. Acreditar baseline y fuente exacta en el entorno privado.
3. Revisar licencia, seguridad, accesibilidad y costes.
4. Reservar propietario/archivos sin duplicidad.
5. Aprobar manifiesto por el Soberano.
6. Construir unidad pequeña y reversible en rama privada.
7. Juez independiente reproduce pruebas sobre HEAD exacto.
8. El Soberano conserva las decisiones reservadas de firma, merge y despliegue.

**Nunca convertir la aprobación de un estudio público en permiso para modificar el repositorio privado.**
