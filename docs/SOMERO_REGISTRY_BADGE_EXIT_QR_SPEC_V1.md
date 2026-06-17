# SOMERO_REGISTRY_BADGE_EXIT_QR_SPEC_V1

## 0. Estado

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: design_only_somero_registry_badge_exit_qr_spec
  runtime_change: false
  code_suggestions: forbidden
  backend: forbidden_now
  private_account_claim: forbidden
  personal_comment_storage: forbidden
  creator_review_required_before_build: true
  source_of_truth: playable_game_state
```

Este documento integra logros, badges, descubrimientos y estado de avance al Somero ID, al QR de salida y al resumen de reentrada. No crea base de datos central ni implementa código.

---

## 1. Principio: el nombre es el sistema de registro

```yaml
somero_registry_principle:
  core: el_nombre_es_el_sistema_de_registro
  display_identity: BADGE_NAME#CFG8
  recovery_method: nombre_mas_palabras_codigo_mas_hash
  database_model: distributed_by_classification
  immediate_database: somero_state_payload

  not_required:
    - large_central_database
    - private_account
    - personal_identity_backup
    - image_or_file_assets
    - personal_comments
```

El nombre de juego no solo identifica al avatar: también apunta a una configuración, una clasificación de avance y una huella de recuperación.

---

## 2. Badges y logros como palabras/tokens del QR

```yaml
badge_achievement_token_model:
  token_sources:
    - discovery_badges
    - achievement_badges
    - story_knowledge_tokens
    - portal_moment_tokens
    - save_point_tokens
    - object_state_tokens
    - role_progress_tokens

  token_properties:
    compact: true
    internal_dictionary_only: true
    no_personal_free_text: true
    no_external_assets: true
    QR_integrable: true

  examples:
    discovery_badges:
      - DISC_BOX_TO_SCALE
      - DISC_SCANNER_VARIATION
      - DISC_POSAYA_AGENCY
      - DISC_PR_WORM_SPLIT

    achievement_badges:
      - ACH_FIRST_DELIVERY
      - ACH_BOX_GOAL_SNAP
      - ACH_WATER_BREAK
      - ACH_POMODORO_1
      - ACH_STUFFBOX_UNLOCK

    portal_moment_tokens:
      - PORTAL_A_BOX
      - PORTAL_B_GOAL
      - PORTAL_MEETING_01

    save_point_tokens:
      - SAVE_OPEN_WAREHOUSE_START
      - SAVE_SCALE_AREA
      - SAVE_DESK_STUFFBOX
      - SAVE_STAGE_2_ENTRY
```

Los badges no son imágenes. Son tokens internos compactos que pueden convertirse en palabras de recuperación, logros visibles o datos del QR de salida.

---

## 3. Base distribuida por clasificación

```yaml
distributed_classification_database:
  meaning: no_guardar_todo_en_un_gran_backend_central

  catalogs:
    avatar_catalog:
      contains:
        - base_forms
        - uniform_variants
        - palette_ids
        - pattern_ids
        - internal_texture_ids

    gizmo_catalog:
      contains:
        - PosAya_states
        - lens_modes
        - display_faces
        - sensor_faces
        - output_faces

    story_catalog:
      contains:
        - chapter_ids
        - scene_ids
        - discovery_tokens
        - knowledge_tokens
        - PR_Worm_flags

    world_catalog:
      contains:
        - checkpoint_ids
        - station_states
        - object_states
        - portal_states

    badge_catalog:
      contains:
        - achievement_tokens
        - discovery_badges
        - role_badges
        - relationship_badges

  somero_state_payload:
    role: base_somera_inmediata
    contains_only_ids_and_tokens: true
```

La base distribuida es un conjunto de catálogos internos. El Somero State Payload solo guarda IDs y tokens de clasificación; no necesita replicar todos los datos del jugador.

---

## 4. Estado somero inmediato del jugador

```yaml
somero_immediate_state:
  identity:
    display_name: BADGE_NAME#CFG8
    selected_words: array_internal_words
    config_hash: CFG8_or_full_hash

  context_snapshot:
    estate: current_state_summary
    checkpoint: save_point_id
    player_position_bucket: string
    time_context: moment_token
    active_portal_context: portal_token_or_none

  progress_snapshot:
    latest_discovery: discovery_token
    latest_goal: goal_token
    latest_knowledge: knowledge_token
    latest_record: record_token

  render_snapshot:
    avatar_render_ids: internal_ids
    gizmo_render_ids: internal_ids
    room_or_area_id: internal_id

  object_snapshot:
    box_state: token
    scale_state: token
    scanner_state: token
    conveyor_state: token
    desk_state: token
    chair_state: token
```

Este payload funciona como una memoria inmediata: suficiente para saber quién soy, dónde estoy, cuándo estoy y qué sigue, sin guardar datos personales ni comentarios libres.

---

## 5. QR de salida con badges y contexto

```yaml
exit_QR_payload:
  payload_type: CHRONORIFT_SOMERO_EXIT_QR
  schema_version: 1

  includes:
    - display_name
    - selected_words
    - config_hash
    - checkpoint
    - player_position_bucket
    - time_context
    - active_portal_context
    - latest_discovery
    - latest_goal
    - latest_knowledge
    - latest_record
    - achievement_badges
    - discovery_badges
    - story_tokens
    - object_state_summary
    - avatar_render_ids
    - gizmo_render_ids

  excludes:
    - personal_comments
    - images
    - files
    - external_textures
    - private_tokens
    - real_identity_data

  display_warning: QR_is_recovery_code_not_private_account
```

El QR de salida debe representar el estado somero actual. No contiene imágenes ni archivos; solo nombre, palabras, hash, tokens y estado resumido.

---

## 6. Texto de salida copiable

```yaml
exit_text_packet_shape:
  title: CHRONORIFT_SOMERO_EXIT_RECORD

  sections:
    - who_am_i
    - where_am_i
    - when_am_i
    - what_changed
    - what_do_i_know_now
    - what_is_next
    - badges_and_discoveries
    - checkpoint_and_objects
    - restore_code
```

Suggested player-facing text:

```text
CHRONORIFT_SOMERO_EXIT_RECORD
This is not a private account. Save this text or QR to restore this Somero state.

WHO AM I: {BADGE_NAME#CFG8}
WORDS: {WORD_1} {WORD_2} {WORD_3}
HASH: {CONFIG_HASH}

WHERE AM I: {AREA_ID} / {PLAYER_POSITION_BUCKET}
WHEN AM I: {MOMENT_TOKEN}
PORTAL CONTEXT: {PORTAL_TOKEN_OR_NONE}
SAVE POINT: {CHECKPOINT_ID}

LATEST DISCOVERY: {DISCOVERY_TOKEN}
NEW GOAL: {GOAL_TOKEN}
NEW KNOWLEDGE: {KNOWLEDGE_TOKEN}
LAST RECORD: {RECORD_TOKEN}

BADGES: {ACHIEVEMENT_BADGES}
STORY: {STORY_TOKENS}
OBJECTS: box={BOX_STATE}; scale={SCALE_STATE}; scanner={SCANNER_STATE}; conveyor={CONVEYOR_STATE}; desk={DESK_STATE}; chair={CHAIR_STATE}

WHAT TO DO NEXT: {NEXT_ACTION_HINT}
```

---

## 7. Login transition summary

```yaml
login_transition_summary:
  trigger:
    - new_login
    - restore_from_text
    - restore_from_QR
    - continue_from_local_state

  shows_while_transitioning_to_game:
    who_am_i:
      source: display_name_and_avatar_summary
      examples:
        - badge_name
        - avatar_uniform
        - STUFFBOX_state

    where_am_i:
      source: checkpoint_and_position_bucket
      examples:
        - open_warehouse_receiving
        - scale_area
        - scanner_station
        - desk_STUFFBOX

    when_am_i:
      source: moment_token_and_portal_context
      examples:
        - before_first_scan
        - after_scanner_variation
        - after_first_delivery
        - stage_2_entry

    what_changed:
      source: latest_record_and_discovery

    what_do_i_know_now:
      source: latest_knowledge_token

    what_do_i_do_next:
      source: active_goal_token
```

La transición desde login debe ser un pequeño reencuadre narrativo: quién soy, dónde estoy, cuándo estoy y qué hay que hacer.

---

## 8. Render rápido del registro de avance

```yaml
quick_progress_render:
  display_blocks:
    identity_card:
      - BADGE_NAME#CFG8
      - avatar_summary
      - PosAya_summary

    location_card:
      - checkpoint
      - area
      - portal_context

    story_card:
      - latest_discovery
      - latest_knowledge
      - latest_record

    goal_card:
      - new_goal
      - next_action_hint

    badge_card:
      - last_3_badges
      - total_badge_count

  duration:
    minimum: 2_seconds
    skippable_after: 1_second
    max: 8_seconds
```

Este render aparece durante la transición a vista de juego. Debe ser rápido, legible y no bloquear el play loop.

---

## 9. Integración con Phase 1 local-only

```yaml
phase_1_integration:
  update_to_PHAS1_plan:
    - export_text_includes_badges
    - QR_payload_includes_badges
    - login_summary_shows_who_where_when_next
    - Somero_ID_name_is_registry_key
    - story_world_state_is_tokenized

  no_runtime_change_yet: true
  build_requires_creator_approval: true

  recommended_next_build_option:
    A_index_only_local:
      add:
        - Somero_ID_panel
        - export_record_text
        - badge_token_summary
        - login_transition_summary
        - QR_text_fallback_first
      preserve:
        - app_js_v1_8_8
```

---

## 10. Claim prevention copy

```yaml
claim_prevention_copy:
  before_exit: >
    Tu Somero ID es tu registro de avance. Guarda el texto o QR. El juego no usa cuenta privada ni backup central para recuperarte si pierdes tus palabras.

  before_restore: >
    Este resumen reconstruye una configuración somera. Revisa quién eres, dónde estás, cuándo estás y qué sigue antes de entrar al juego.

  before_QR: >
    Este QR contiene tu estado somero: nombre, palabras, hash, badges y checkpoint. No contiene imágenes ni archivos. Quien tenga el QR podría cargar el mismo estado somero.
```

---

## 11. Gates antes de cualquier build

```yaml
before_build_gates:
  - creator_explicit_approval
  - no_claim_of_private_account
  - no_large_central_backup_claim
  - QR_warning_required
  - no_personal_comment_storage
  - no_images_or_files
  - badges_are_tokens_not_external_assets
  - preserve_v1_8_8_box_goal_loop
  - login_summary_must_be_skippable
```
