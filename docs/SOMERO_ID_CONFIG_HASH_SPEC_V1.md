# SOMERO_ID_CONFIG_HASH_SPEC_V1

## 0. Estado

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: design_only_somero_id_configuration_hash_spec
  runtime_change: false
  code_suggestions: forbidden
  identity_extraction: forbidden
  sensitive_exposure: forbidden
  private_ingestion: forbidden
  external_assets: forbidden
  creator_review_required_before_build: true
  source_of_truth: playable_game_state
```

Este documento diseña un sistema de Somero ID y huella de configuración para recuperar avatar, configuraciones y estado de juego sin requerir backup externo del usuario. No implementa código todavía.

---

## 1. Principio central

```yaml
core_principle:
  goal: recuperar_configuracion_sin_backup_externo
  method: nombre_de_juego_mas_palabras_o_codigos_semilla
  output: somero_id_plus_config_hash

  important_boundary:
    hash_is_fingerprint_not_private_authentication: true
    not_a_secure_private_login: true
    not_real_identity: true
    no_personal_data_required: true
```

El hash o SHA funciona como huella determinística y verificador de configuración. No debe presentarse como autenticación privada fuerte ni como cuenta segura. Para configuraciones públicas/locales de juego sí puede funcionar como recuperación somera.

---

## 2. Somero login

```yaml
somero_login:
  player_inputs:
    required:
      - chosen_badge_name
      - recovery_words_or_codes

    optional:
      - preferred_name_structure
      - avatar_seed_style
      - difficulty_or_accessibility_preference

  generated_identity:
    display_format: BADGE_NAME#CFG8
    examples:
      - SOMERO-VALE#A91F20C3
      - NODE-PILGRIM-07#4D22BA19
      - GRAY-TORUS#8F03CD11

  constraints:
    - no_real_name_required
    - no_email_required
    - no_password_required_for_local_recovery
    - no_external_account_binding_required
    - player_can_reroll_or_choose
```

El Somero login no intenta identificar a la persona real. Identifica una configuración jugable y recuperable.

---

## 3. Semillas aleatorias elegibles

```yaml
seed_phrase_model:
  structure_options:
    one_field:
      shape: WORD
      use: configuracion_minima

    two_fields:
      shape: WORD_WORD
      use: configuracion_memorable

    three_fields:
      shape: WORD_WORD_NUMBER_OR_GLYPH
      use: configuracion_mas_estable

  word_sources:
    allowed:
      - word_list_local_del_juego
      - glyph_list_local_del_juego
      - numeric_code_local
      - player_selected_from_list
      - random_from_allowed_list

    forbidden:
      - personal_sensitive_words
      - uploaded_files
      - external_images
      - external_textures
      - external_mods
      - private_system_tokens
```

Las palabras/códigos deben venir de listas internas del juego o selección manual del jugador. No se aceptan archivos, imágenes, texturas externas ni modificaciones externas.

---

## 4. Configuración canónica

```yaml
canonical_config_payload:
  avatar:
    - badge_name
    - body_base
    - uniform_variant
    - color_palette_id
    - pattern_id
    - texture_id_internal_only
    - brightness_luma
    - personal_items_equipped
    - STUFFBOX_items_unlocked

  gizmo:
    - PosAya_state
    - folded_state
    - display_face_style
    - sensor_face_style
    - output_face_style
    - lens_mode_preferences

  controls:
    - preferred_view
    - touch_layout_id
    - accessibility_assist_level
    - camera_sensitivity_bucket

  progression:
    - attributes
    - training_unlocks
    - recovery_unlocks
    - self_help_instruments_unlocked

  story_state:
    - chapter_id
    - scene_id
    - agency_realization_flags
    - PR_Worm_revelation_flags
    - PosAya_relationship_flags

  world_state:
    - checkpoint_id
    - player_position_bucket
    - open_warehouse_station_state
    - object_state_summary
    - box_state
    - conveyor_state
    - scale_state
    - scanner_state
    - desk_state
```

La configuración debe serializarse en un orden fijo y estable para que el mismo nombre y semilla produzcan el mismo resultado.

---

## 5. Huella SHA / hash de configuración

```yaml
configuration_hash_model:
  input_to_hash:
    - canonical_config_payload
    - chosen_badge_name
    - recovery_words_or_codes
    - game_version_namespace

  output:
    short_display_hash: first_8_or_10_chars
    full_hash: optional_for_export
    display_format: BADGE_NAME#CFG8

  use:
    - identify_configuration
    - detect_typing_or_recovery_mismatch
    - restore_deterministic_options
    - compare_versions

  not_use:
    - not_private_authentication
    - not_secret_storage
    - not_payment_identity
    - not_private_user_backup
```

El hash puede entenderse como una llave semántica de configuración, no como contraseña. Si alguien conoce el nombre y las palabras/códigos, podría reconstruir la misma configuración; por eso no debe guardar datos sensibles.

---

## 6. Recuperación sin backup

```yaml
recovery_flow:
  player_enters:
    - badge_name
    - recovery_words_or_codes

  system_rebuilds:
    - avatar_base
    - internal_texture_ids
    - color_palette
    - controls_preference
    - STUFFBOX_unlocked_set
    - story_state_if_encoded
    - checkpoint_state_if_encoded

  player_confirms:
    - preview_avatar
    - preview_badge
    - preview_gizmo_state
    - continue_or_reroll

  limitations:
    - cannot_restore_external_assets
    - cannot_restore_unencoded_manual_notes
    - cannot_restore_private_data
    - cannot_prove_real_identity
```

La recuperación funciona mejor para configuraciones enumeradas por el juego. No está diseñada para respaldar identidad privada real.

---

## 7. Registro de historia y mundo

```yaml
story_world_state_registry:
  can_encode:
    - story_progress
    - scene_flags
    - checkpoint_id
    - player_position_bucket
    - object_states
    - station_states
    - box_delivery_state
    - STUFFBOX_unlocks
    - PosAya_relationship_state

  position_encoding:
    preferred: bucket_or_checkpoint_not_exact_sensitive_trace
    examples:
      - warehouse_receiving_zone
      - scale_area
      - scanner_station
      - desk_station
      - conveyor_zone
      - stage_2_entry

  object_state_encoding:
    examples:
      box: at_scale_or_at_belt_or_delivered
      scale: empty_or_box_weighed
      scanner: idle_or_reading_or_flagged
      conveyor: off_or_ready_or_running
      desk: locked_or_unlocked
      chair: unavailable_or_available
```

Se puede registrar avance de historia, posición y estado de objetos, pero como estado de juego y checkpoint, no como rastreo real del usuario.

---

## 8. Restricciones de assets y modificaciones

```yaml
asset_restrictions:
  allowed:
    - internal_color_ids
    - internal_pattern_ids
    - internal_texture_ids
    - internal_uniform_variants
    - internal_STUFFBOX_items
    - internal_avatar_parts
    - internal_gizmo_parts

  forbidden:
    - uploaded_images
    - external_files
    - external_textures
    - user_mods
    - executable_modifications
    - unreviewed_scripts
    - private_tokens
```

La personalización puede ser rica, pero debe basarse en catálogos internos. El sistema no acepta imágenes, archivos, texturas externas ni modificaciones externas.

---

## 9. Relación con avatar y gizmo

```yaml
avatar_gizmo_config_relation:
  avatar_config:
    - neutral_base
    - company_uniform
    - badge_id
    - STUFFBOX_personalization
    - fold_unfold_state

  gizmo_config:
    - PosAya_visual_state
    - reader_lens_mode
    - display_sensor_output_face
    - fold_unfold_state

  shared_config:
    - color_palette_id
    - pattern_family
    - relationship_state
    - story_flags
    - accessibility_preference
```

El Somero ID puede codificar la relación visual y narrativa entre el avatar y Pos.Aya.

---

## 10. Seguridad narrativa y técnica

```yaml
safety_boundary:
  required:
    - no_real_identity_required
    - no_sensitive_data
    - no_private_ingestion
    - no_external_assets
    - no_code_from_comments
    - no_runtime_mutation_without_creator_approval
    - preserve_v1_8_8_box_goal_loop

  language_rule:
    - call_it_recovery_code_or_configuration_fingerprint
    - do_not_call_it_secure_private_account
    - do_not_claim_it_prevents_impersonation
```

---

## 11. Superconglomerado decisional

```yaml
superconglomerado_decisional:
  option_id: SOMERO_ID_CONFIG_HASH_SPEC_V1
  hashtags:
    - "#someroid"
    - "#config_hash"
    - "#avatar"
    - "#stuffbox"
    - "#posaya"
    - "#checkpoint"
    - "#populares"

  semantic_desire: crear_un_nombre_badge_con_hash_configurable_para_recuperar_avatar_gizmo_historia_posicion_y_estado_de_objetos_sin_backup_externo

  creator_question: debe_el_login_somero_usar_nombre_mas_palabras_codigo_para_reconstruir_configuracion_sin_aceptar_assets_externos_ni_datos_sensibles

  branches:
    A_design_only:
      meaning: refinar_modelo_sin_codigo
      risk: low

    B_seed_dictionary_spec:
      meaning: definir_listas_internas_de_palabras_codigos_y_estructuras_de_nombre
      risk: low

    C_canonical_payload_spec:
      meaning: definir_payload_canonico_para_avatar_gizmo_historia_y_estado_de_objetos
      risk: low_medium

    D_future_runtime_candidate:
      meaning: solo_despues_de_aprobacion_separada_para_build
      risk: medium

  approval_status:
    state: pending_creator_review
```

---

## 12. Gates antes de cualquier build

```yaml
before_build_gates:
  - creator_explicit_approval
  - hash_not_presented_as_secure_private_auth
  - no_real_identity_required
  - no_sensitive_data
  - no_external_assets
  - no_private_ingestion
  - no_code_from_comments
  - preserve_v1_8_8_box_goal_loop
```
