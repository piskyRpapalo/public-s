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
# Campos opcionales de Ideas26nov y Ronda 4, no permisos
source_round: "NO_DATA(round4_not_received)"
source_label: "SOURCE"   # SOURCE / VERIFIED / INFERENCE
source_version: "NO_DATA(not_received)"
unit_id: "NO_DATA(unassigned)"  # U11–U14 solo si aparecen en la fuente real
skills_schema_version: "PROPOSED"
deny_conditions:
  - "No hay autorización efectiva para actuar"
  - "Falta prueba o atribución del iniciador"
prompt_version: "NO_DATA(not_modified)"
md_files_touched: []
baseline_prompt_digest: "NO_DATA(not_measured)"
proposed_prompt_digest: "NO_DATA(not_built)"
rollback_prompt_digest: "NO_DATA(not_built)"
evolution_proposal_ref: "NO_DATA(not_created)"
task_extension_version: "NO_DATA(not_negotiated)"
browser_profile_isolation: "NO_DATA(not_tested)"
destination_hash_gate: "PENDING"
visual_provenance:
  asset_kind: "NO_DATA(not_created)"  # screenshot_real | diagram_proposed | storyboard_synthetic | video_verified
  source_artifact_head: "NO_DATA(not_verified)"
  source_observed_at: "NO_DATA(not_verified)"
  alt_text_verified: false
  publication_license: "NO_DATA(not_reviewed)"
video_event_provenance: "NO_DATA(no_event_verified)"
cinek_independent_governance_preserved: true
candidate_roles_not_activated: ["S_VISION", "T_MOTION", "N_VIGIA", "O_ADUANA"]
existing_role_L_utility_contract_preserved: true
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

## Extensión opcional · Ronda 4 visual, cine y continuidad

La [guía de Ronda 4](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md) **no modifica el contrato privado**. Para proponer una pieza visual o transferencia entre repositorios, anexar estos campos al manifiesto de ejemplo y conservar el resto del gate:

```yaml
idea_source: "Ideas26nov Parte 4 | NO_DATA(source_not_received)"
source_label: "SOURCE | VERIFIED | INFERENCE"
domain: "visual_identity | cine_local | repo_continuity | other"
consumer_repo: "repositorio público o referencia no sensible"
producer_repo: "referencia de origen revisada, sin ruta privada"
owner_existing: "titular del producto, no nuevo proceso"
role_candidate: "S | T | none" # S/T PROPOSED
reuse_justification: "qué pipeline/componente existente evita duplicación"
artifact_kind: "real_capture | diagram | storyboard_fixture | video | report"
artifact_origin: "versión/commit/digest y fecha o NO_DATA(cause)"
is_simulated: true
event_receipt_verified: "NO_DATA(not_verified)"
release_provenance: "NO_DATA(not_verified)"
cinek_independence_preserved: true
app_mvp_scope_respected: true
accessibility:
  alt_text_reviewed: "NO_DATA(not_tested)"
  captions_reviewed: "NO_DATA(not_applicable_or_tested)"
  same_semantic_state_across_channels: "NO_DATA(not_tested)"
media_rights: "NO_DATA(not_reviewed)"
current_gpu_runtime: "NO_DATA(not_verified)"
publication_approval: "PENDING"
destination_hash_verified: "NO_DATA(not_merged)"
benefit_metric:
  useful_deltas_per_repo: "NO_DATA(not_measured)"
  generation_minutes: "NO_DATA(not_measured)"
  energy_wh_measured: "NO_DATA(not_measured)"
  energy_wh_estimated: "NO_DATA(not_measured)"
  visually_accessible_share: "NO_DATA(not_measured)"
```

**Condiciones especiales:** S/T son candidaturas, nunca identidades autorizadas por un campo YAML. L conserva su rol de juicio de utilidad. CineK mantiene gobierno independiente; cualquier convergencia o archivo requiere otro proceso de decisión. No usar eventos reales sin permiso, ni gastar GPU o publicar contenido porque haya pasado una prueba de storyboard. La Parte 4 no está recibida; tampoco se presuponen los contratos U11–U14.

## Campos del traspaso de ronda 4

Los campos anteriores son **opciones de estudio** para [la guía general Ronda 4](PREPARACION-IDEAS26NOV-RONDA4-2026-11-26.md) y el [complemento visión/CineK](PREPARACION-IDEAS26NOV-RONDA4-VISUAL-ECOSISTEMA-2026-11-26.md), no una especificación de runtime. Un nombre de rol candidato no lo instala, ni un digest equivale a firma. Si la futura fuente no define U11–U14, mantener `NO_DATA(source_round4_U11_U14_text_not_received)`. Antes de modificar el contrato privado se requiere diff contra HEAD real, propietario, revisión independiente y decisión soberana separada. No activar S/T ni alterar la autonomía de CineK por rellenar una plantilla.
