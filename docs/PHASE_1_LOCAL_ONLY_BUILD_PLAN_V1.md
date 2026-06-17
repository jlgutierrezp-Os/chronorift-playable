# PHASE_1_LOCAL_ONLY_BUILD_PLAN_V1

## 0. Estado

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: build_plan_before_runtime_change
  runtime_change: false
  code_suggestions: forbidden
  backend: forbidden_now
  personal_comment_storage: forbidden
  image_file_sharing: forbidden
  external_assets: forbidden
  private_account_claim: forbidden
  creator_review_required_before_build: true
  source_of_truth: playable_game_state
```

Este documento convierte la ruta aprobada `phase_1_local_only` en un plan de build. No modifica runtime todavía. La implementación futura requiere aprobación explícita de @Creador.

---

## 1. Objetivo de Phase 1

```yaml
phase_1_goal:
  name: local_only_somero_recovery_and_preset_social_rooms
  objective:
    - crear_Somero_ID_local
    - permitir_exportar_texto_de_recuperacion
    - permitir_guardar_archivo_txt_local
    - mostrar_QR_local_del_codigo_somero
    - simular_Lunch_Room_con_frases_preset
    - preservar_v1_8_8_box_goal_loop

  not_objective:
    - no_real_public_chat
    - no_backend
    - no_private_account
    - no_password_auth
    - no_image_upload
    - no_file_upload
    - no_external_mods
```

---

## 2. UI flow

```yaml
UI_flow:
  entry_screen:
    title: ChronoRift Somero ID
    copy: este_juego_no_crea_cuenta_privada
    actions:
      - crear_nuevo_Somero_ID
      - continuar_con_codigo
      - jugar_sin_Somero_ID
      - leer_aviso

  create_somero_id:
    steps:
      - elegir_estructura_de_nombre
      - elegir_o_generar_palabras_codigo
      - previsualizar_badge
      - previsualizar_hash
      - confirmar_que_no_es_cuenta_privada
      - copiar_o_guardar_codigo
      - continuar_al_juego

  continue_with_code:
    steps:
      - ingresar_badge_name
      - ingresar_palabras_codigo
      - opcional_escanear_QR_local
      - reconstruir_preview_somero
      - confirmar_continuar
      - cargar_checkpoint_codificado_si_existe

  in_game_menu:
    actions:
      - ver_Somero_ID
      - copiar_codigo
      - guardar_txt
      - mostrar_QR
      - abrir_Lunch_Room_local
      - abrir_Cubiculo
      - apagar_equipo_y_salir

  exit_flow:
    steps:
      - mostrar_resumen_de_estado
      - advertir_guardar_antes_de_salir
      - copiar_texto
      - guardar_txt
      - mostrar_QR
      - salir_sin_guardar_con_confirmacion
```

---

## 3. Recovery payload shape

```yaml
recovery_payload_shape:
  schema_version: 1
  payload_type: CHRONORIFT_SOMERO_RECOVERY

  identity:
    badge_name: string
    name_structure: enum_1_2_3_fields
    recovery_words_or_codes: array_internal_words
    config_hash_short: string

  game:
    build_namespace: ChronoRift
    runtime_safe_point: v1.8.8_box_goal_snap_assist_stage_transition
    checkpoint_id: string
    player_position_bucket: string

  avatar:
    base_id: string
    uniform_id: string
    palette_id: string
    pattern_id: string
    texture_id_internal_only: string
    STUFFBOX_items: array_internal_ids
    fold_state: folded_or_semifolded_or_unfolded

  gizmo:
    PosAya_state: string
    lens_mode: string
    display_face_id: string
    sensor_face_id: string
    output_face_id: string

  progress:
    story_flags: array_tokens
    achievement_tokens: array_tokens
    discovery_tokens: array_tokens
    pomodoro_preference: string

  world:
    object_state_summary:
      box: string
      scale: string
      scanner: string
      conveyor: string
      desk: string
      chair: string

  integrity:
    canonical_order_required: true
    hash_is_fingerprint_not_auth: true
```

---

## 4. Export text shape

```yaml
export_text_shape:
  title: CHRONORIFT_SOMERO_ID_EXPORT

  sections:
    - warning
    - display_name
    - recovery_words
    - config_hash
    - checkpoint
    - avatar_summary
    - gizmo_summary
    - story_discoveries
    - achievements
    - object_state_summary
    - instructions_to_restore

  excludes:
    - personal_free_text_comments
    - uploaded_images
    - files
    - external_textures
    - private_tokens
    - real_identity_data
```

Suggested export text:

```text
CHRONORIFT_SOMERO_ID_EXPORT
This is not a private account. Save this text. If you lose it, the game cannot recover your Somero state.

DISPLAY_NAME: {BADGE_NAME#CFG8}
RECOVERY_WORDS: {WORD_1} {WORD_2} {WORD_3}
CONFIG_HASH: {CFG8_OR_FULL_HASH}
CHECKPOINT: {CHECKPOINT_ID}
POSITION: {PLAYER_POSITION_BUCKET}
AVATAR: {AVATAR_CONFIG_IDS}
POSAYA: {GIZMO_CONFIG_IDS}
STUFFBOX: {UNLOCKED_ITEM_IDS}
POMODORO: {PREFERENCE_ID}
STORY_DISCOVERIES: {TOKENS}
ACHIEVEMENTS: {TOKENS}
OBJECTS: box={BOX_STATE}; scale={SCALE_STATE}; scanner={SCANNER_STATE}; conveyor={CONVEYOR_STATE}; desk={DESK_STATE}; chair={CHAIR_STATE}

RESTORE:
Open ChronoRift > Continue with code > enter badge name and recovery words, or scan your local QR if you saved it.
```

---

## 5. Save file warning copy

```yaml
save_file_warning_copy:
  title: Guardar Somero ID
  body: >
    Este archivo contiene tu nombre de juego, palabras/códigos y estado somero. No es una cuenta privada. Guárdalo si quieres retomar después. Si lo pierdes, el juego no puede recuperarlo por ti.

  buttons:
    - Guardar archivo .txt
    - Copiar texto
    - Mostrar QR local
    - Volver
```

---

## 6. QR warning copy

```yaml
QR_warning_copy:
  title: QR de recuperación somera
  body: >
    Este QR puede restaurar la misma configuración somera. No es contraseña ni cuenta privada. Si otra persona tiene este QR, podría cargar el mismo estado somero. Guárdalo solo donde tú decidas.

  QR_types:
    site_access_QR:
      content: public_game_url
      risk: low

    user_resume_QR:
      content: compact_somero_payload_or_recovery_code
      risk: medium
      requires_warning: true
```

---

## 7. Local Lunch Room preset phrases

```yaml
local_lunch_room_preset_phrases:
  room_type: local_simulated_or_preset_only
  free_text_default: false
  personal_comment_storage: false

  categories:
    greeting:
      - Hola, tomo descanso breve.
      - Buen turno.
      - Me siento en esta mesa.
      - Regreso al trabajo en un momento.

    work_light:
      - Estoy ordenando cajas.
      - Estoy practicando escaneo.
      - Necesito revisar la banda.
      - Voy a pesar una caja más.

    water_break:
      - Voy por agua.
      - Pausa corta.
      - Respiro y vuelvo.
      - Descanso de ojos.

    cooperation:
      - ¿Alineamos esta caja?
      - Yo tomo este lado.
      - Tú toma el otro lado.
      - Listo para sincronizar.

    pomodoro:
      - Inicio bloque de trabajo.
      - Inicio descanso.
      - Terminé mi pausa.
      - Continúo después del timer.

    posaya:
      - Pos.Aya está leyendo la superficie.
      - Pos.Aya sugiere revisar el estado.
      - Voy a comparar la lectura.
      - Cancelar sin castigo.

    boundaries:
      - No comparto datos personales.
      - Solo uso frases someras.
      - No envío archivos.
      - No subo imágenes.
```

---

## 8. Regression gate: preserve v1.8.8 box-goal loop

```yaml
regression_gate_preserve_v1_8_8_box_goal_loop:
  must_preserve:
    - caja_agarrable
    - caja_menos_resbalosa
    - caja_cruza_portal
    - asistencia_visible_hacia_meta
    - snap_lock_en_meta_verde
    - declaracion_PUZZLE_RESUELTO
    - STAGE_2_DESBLOQUEADO
    - matriz_cardinal_de_portales

  forbidden_regressions:
    - menu_Somero_bloquea_controles_del_juego
    - Lunch_Room_bloquea_movimiento_o_grab
    - export_overlay_no_cierra
    - QR_overlay_no_cierra
    - guardar_o_salir_rompe_checkpoint
    - cambios_en_app_js_sin_aprobacion

  minimum_test_before_release:
    - abrir_juego
    - cerrar_menu_Somero
    - mover_player
    - agarrar_caja
    - colocar_portal_A
    - colocar_portal_B
    - pasar_caja_por_portal
    - llevar_caja_a_meta
    - observar_PUZZLE_RESUELTO
    - observar_STAGE_2_DESBLOQUEADO
    - abrir_export
    - cerrar_export
    - continuar_jugando
```

---

## 9. Implementation sequencing candidate

```yaml
implementation_sequence_candidate:
  step_1:
    name: add_non_blocking_Somero_panel_to_index
    runtime_file: index_html_only_preferred
    risk: low_medium

  step_2:
    name: local_payload_and_export_text_generation
    runtime_file: index_html_inline_or_small_local_module
    risk: low_medium

  step_3:
    name: save_txt_file_button
    runtime_file: index_html_or_local_helper
    risk: low_medium

  step_4:
    name: QR_local_display
    runtime_file: index_html_or_local_helper
    risk: medium
    note: may_require_small_embedded_QR_generator_or_text_fallback

  step_5:
    name: local_lunch_room_preset_only
    runtime_file: index_html_overlay
    risk: low_medium

  blocked:
    phase_2_async_public_room:
      until:
        - backend_review
        - data_policy
        - moderation_policy
        - creator_explicit_approval
```

---

## 10. Approval requested before runtime build

```yaml
creator_next_decision:
  options:
    A_approve_phase_1_build_index_only:
      meaning: build_non_blocking_local_Somero_export_QR_and_preset_Lunch_Room_in_index_html_without_touching_app_js
      risk: low_medium

    B_approve_phase_1_build_split_file:
      meaning: add_small_local_module_file_for_Somero_system_and_keep_index_cleaner
      risk: medium

    C_keep_design_only:
      meaning: refine_plan_without_runtime_change
      risk: low

    D_defer:
      meaning: wait_until_core_runtime_compaction
      risk: low

  recommendation:
    - A_approve_phase_1_build_index_only_first
    - preserve_app_js_v1_8_8
    - if_QR_library_is_too_large_use_text_fallback_first
```

---

## 11. Gates antes de cualquier build

```yaml
before_build_gates:
  - creator_explicit_approval
  - no_claim_of_private_account
  - no_personal_comment_storage
  - no_images_or_files
  - no_external_assets
  - no_backend_public_chat
  - QR_warning_required
  - export_prompt_required_before_exit
  - preserve_v1_8_8_box_goal_loop
  - prefer_index_html_only_first
```
