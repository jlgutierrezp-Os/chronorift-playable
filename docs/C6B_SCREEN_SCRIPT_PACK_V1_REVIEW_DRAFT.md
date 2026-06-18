# C6B_SCREEN_SCRIPT_PACK_V1_REVIEW_DRAFT

Status: auto-filled human review draft. No runtime replacement. No gameplay build yet.

## Purpose

Create the exact screen text, dialogue boxes, menu labels, icons, indicators, achievement hooks, badge hooks, and test packet for C6B_RPG_ONBOARDING_FOUNDATION.

This document is intentionally editable. Each section includes:

- AUTO_FILL: recommended content based on current project context.
- AUTO_COMMENT: why this recommendation exists.
- HUMAN_COMMENT: space for user review, correction, acceptance, or replacement.

## Operating rule for this interaction type

```yaml
REVIEW_LOOP_RULE:
  every_user_comment_after_this:
    - interpret_structurally
    - classify_as_accept_revise_remove_add_or_question
    - integrate_into_draft
    - preserve_original_design_intent
    - return_updated_section_for_approval
  build_allowed: false
  build_condition:
    - human_accepts_screen_script_pack
    - then_generate_C6B_minimal_playable_web_build
```

---

# 0. C6B scope lock

```yaml
C6B_SCOPE_LOCK:
  include:
    - corporate_intro_card
    - application_identity_screen
    - avatar_placeholder
    - personal_items_screen
    - Stuff_Box_locker_transition
    - cubicle_hub
    - notebook_Somero_entry
    - laptop_menu
    - supervisor_first_email
    - boss_welcome_message
    - PR_Worm_first_harmless_nudge
    - Pos_Aya_first_hint
    - recovery_choice_seed
    - review_report
  exclude:
    - package_batches
    - box_transport
    - stacking_boxes
    - labeling_scale_color_zones
    - construction
    - repair_minigames
    - portals
    - time_systems
    - full_PR_Worm_escalation
    - full_Pos_Aya_reveal
    - final_endings
```

AUTO_COMMENT: C6B must stabilize story onboarding and navigation before any heavy gameplay systems return.

HUMAN_COMMENT:

---

# 1. Global UI language

## 1.1 Tone

AUTO_FILL:

ChronoRift C6B uses friendly corporate language that slowly feels too permanent. The player should feel amused, slightly suspicious, and curious. The UI should look helpful but reveal small signs that the loop is not neutral.

AUTO_COMMENT: This protects the corporate satire while avoiding full PR Worm escalation too early.

HUMAN_COMMENT:

## 1.2 Primary labels

```yaml
PRIMARY_LABELS:
  start: INICIAR
  apply: APLICAR
  continue: CONTINUAR
  next: SIGUIENTE
  back: VOLVER
  inspect: INSPECCIONAR
  store: GUARDAR EN STUFF BOX
  close_locker: CERRAR LOCKER
  open_notebook: ABRIR NOTEBOOK
  open_laptop: ABRIR LAPTOP
  stand_up: LEVANTARSE
  sit_down: VOLVER AL ESCRITORIO
  open_gizmo: ABRIR POS.AYA
  review: ENVIAR REVIEW
```

AUTO_COMMENT: Labels are short, mobile-friendly, and compatible with Spanish primary UI while preserving branded English terms.

HUMAN_COMMENT:

## 1.3 Core icons

```yaml
CORE_ICONS:
  Corporation: 🏢
  Loop: 🔁
  Human: 👤
  Stuff_Box: 📦
  Personal_Items: 🎒
  Notebook_Somero: 📓
  Laptop_Mail: 💻
  Supervisor: 👁️
  Boss: 🪑
  PR_Worm: 🪱
  Pos_Aya: ◉
  Energy: ⚡
  Recovery: 🌱
  Achievement: ★
  Badge: ◆
  Warning: ⚠
  Locked_Future_App: 🔒
```

AUTO_COMMENT: Icons are provisional and low-processor. They can later be replaced with custom SVG/icon art.

HUMAN_COMMENT:

---

# 2. Screen A — Corporate intro card

## 2.1 Screen goal

AUTO_FILL:

Introduce the Corporation, the phrase HUMAN in the LOOP, and the promise of easy work. The screen should feel like a friendly online job ad.

AUTO_COMMENT: This is the first satire beat. It must be readable and light, not dark immediately.

HUMAN_COMMENT:

## 2.2 Exact screen text

```text
🏢 CORPORATION PRESENTA

HUMAN in the LOOP

No necesitas experiencia.
No necesitas entender todo.
Solo necesitas estar disponible.

Únete como Trainee de Supervisión Operativa.
Aprende trabajando.
Gana coins.
Ayuda a optimizar un sistema que siempre necesita a alguien.
```

AUTO_COMMENT: “Solo necesitas estar disponible” introduces the danger softly. “Trainee de Supervisión Operativa” prepares the later self-supervision twist.

HUMAN_COMMENT:

## 2.3 Buttons

```yaml
BUTTONS:
  primary: APLICAR
  secondary: LEER OFERTA
  optional: OMITIR INTRO
```

AUTO_COMMENT: “Omitir intro” supports active players who prefer no reading.

HUMAN_COMMENT:

## 2.4 Achievement hooks

```yaml
ACHIEVEMENT_HOOKS:
  First_Application:
    trigger: player_taps_APLICAR
    popup: "★ First Application — Entraste al proceso."
```

HUMAN_COMMENT:

---

# 3. Screen B — Application and identity

## 3.1 Screen goal

AUTO_FILL:

Let the player enter or confirm a name. Present the name as a Somero trace anchor, not as external account identity.

AUTO_COMMENT: This protects privacy and makes the name-word ledger meaningful from the start.

HUMAN_COMMENT:

## 3.2 Exact screen text

```text
FORMULARIO DE INGRESO

Nombre de uso dentro del Loop:
[________________]

Este nombre será usado para tu Somero Trace.
No es contraseña.
No es cuenta.
Es una marca para recordar dónde estabas.
```

AUTO_COMMENT: Explicitly says this is not password/account. It prepares future Somero recovery.

HUMAN_COMMENT:

## 3.3 Suggested default if player leaves empty

```yaml
DEFAULT_NAME_OPTIONS:
  - Sairen
  - Trainee
  - Human_01
```

AUTO_COMMENT: Uses Sairen only as symbolic/default option, not forced legal identity.

HUMAN_COMMENT:

## 3.4 Buttons

```yaml
BUTTONS:
  primary: GUARDAR NOMBRE
  secondary: USAR HUMAN_01
  next: CONTINUAR A AVATAR
```

HUMAN_COMMENT:

---

# 4. Screen C — Avatar placeholder

## 4.1 Screen goal

AUTO_FILL:

Create an avatar seed without final customization. Keep it low-processor and symbolic.

AUTO_COMMENT: Avoid spending too much time on art/customization before the flow works.

HUMAN_COMMENT:

## 4.2 Exact screen text

```text
AVATAR TEMPORAL

Tu avatar no necesita estar completo para empezar.
La Corporation solo necesita una silueta operativa.
Tú puedes recuperar el resto después.
```

AUTO_COMMENT: Satire: corporation reduces person to silhouette; story later restores identity.

HUMAN_COMMENT:

## 4.3 Avatar options

```yaml
AVATAR_OPTIONS:
  silhouette_worker: "👤 Trainee"
  geometric_worker: "◇ Operador"
  soft_robotic_worker: "◉ Asistente humano"
```

HUMAN_COMMENT:

## 4.4 Achievement / badge hooks

```yaml
ACHIEVEMENT_HOOKS:
  Identity_Seed:
    trigger: avatar_selected
    popup: "★ Identity Seed — La silueta fue registrada."

BADGE_HOOKS:
  Early_Identity_Badge:
    trigger: player_inspects_avatar_details_before_continue
    popup: "◆ Early Identity — Miraste antes de obedecer."
```

HUMAN_COMMENT:

---

# 5. Screen D — Personal items

## 5.1 Screen goal

AUTO_FILL:

Let the player choose personal items. These are not cosmetic only; they are future story tools.

AUTO_COMMENT: This anchors later recovery, chip, anti-worm, family/contact, and agency routes.

HUMAN_COMMENT:

## 5.2 Exact screen text

```text
PERSONAL BELONGINGS

Antes de ingresar al área operativa, guarda tus pertenencias.
La Corporation recomienda viajar ligero.

Algunos objetos parecen inútiles durante el trabajo.
Eso no significa que no importen.
```

AUTO_COMMENT: Introduces Personal Belongings and hints that items will matter later.

HUMAN_COMMENT:

## 5.3 Item cards

```yaml
ITEM_CARDS:
  phone:
    label: "📱 Teléfono"
    text: "Sirve para llamar a alguien cuando recordar el mundo exterior sea necesario."
  sim_chip:
    label: "▣ Chip / SIM"
    text: "Pequeño. Fácil de perder. Difícil de reemplazar."
  tape:
    label: "▤ Cinta"
    text: "Une cosas que no estaban diseñadas para unirse."
  sticks:
    label: "╱╲ Palitos"
    text: "Estructura mínima para una idea improvisada."
  small_flower:
    label: "🌱 Recuerdo vegetal"
    text: "No aumenta productividad. Por eso puede ser importante."
```

AUTO_COMMENT: Added small flower/plant as seed for later bonsai/flower meaning, but can be removed if too early.

HUMAN_COMMENT:

## 5.4 Buttons

```yaml
BUTTONS:
  primary: GUARDAR SELECCIÓN
  secondary: INSPECCIONAR ÍTEM
  next: IR A STUFF BOX
```

HUMAN_COMMENT:

## 5.5 Achievement / badge hooks

```yaml
BADGE_HOOKS:
  Personal_Meaning_Badge:
    trigger: player_selects_all_core_personal_items
    popup: "◆ Personal Meaning — Guardaste más que herramientas."
```

HUMAN_COMMENT:

---

# 6. Screen E — Stuff Box / locker

## 6.1 Screen goal

AUTO_FILL:

Store personal items in the Stuff Box and make the locker a symbolic threshold. Closing the locker starts work mode.

AUTO_COMMENT: This creates the emotional anchor for later retrieval/resistance.

HUMAN_COMMENT:

## 6.2 Exact screen text

```text
STUFF BOX

Tus pertenencias han sido guardadas.
Estado de propiedad: Personal.
Ubicación actual: Stuff Box.
Acceso durante turno: limitado.

Cierra el locker para iniciar tu entrenamiento.
```

AUTO_COMMENT: “Estado de propiedad” prepares later item ownership warnings and PR Worm/supervisor interference.

HUMAN_COMMENT:

## 6.3 Somero trace text

```text
SOMERO TRACE:
{PLAYER_NAME}-STUFFBOX-ITEMS-STORED-ENERGY-STABLE
```

AUTO_COMMENT: Phrase is not auth; it is recoverable state text.

HUMAN_COMMENT:

## 6.4 Buttons

```yaml
BUTTONS:
  primary: CERRAR LOCKER
  secondary: REVISAR PERTENENCIAS
  hidden_future: APP PERSONALIZATION 🔒
```

AUTO_COMMENT: Future App placeholder is visible but locked; it should not ask for account/payment in C6B.

HUMAN_COMMENT:

## 6.5 Achievement hook

```yaml
ACHIEVEMENT_HOOKS:
  Stuff_Box_Ready:
    trigger: locker_closed_after_items_stored
    popup: "★ Stuff Box Ready — Tus pertenencias esperan."
```

HUMAN_COMMENT:

---

# 7. Screen F — Cubicle hub

## 7.1 Screen goal

AUTO_FILL:

Introduce the cubicle as the first RPG hub: desk, notebook, laptop, stand-up action, and first Pos.Aya hint.

AUTO_COMMENT: The player should feel the game has become a place, not just menus.

HUMAN_COMMENT:

## 7.2 Exact screen text

```text
CUBÍCULO DE TRAINEE

Tu estación está lista.
El sistema ha preparado tus primeras herramientas:

📓 Notebook / Somero
💻 Laptop corporativa
◉ Pos.Aya
⬆ Levantarse

Objetivo actual:
Conoce tu estación antes de comenzar a optimizar nada.
```

AUTO_COMMENT: “Antes de optimizar nada” gently resists immediate productivity.

HUMAN_COMMENT:

## 7.3 Menu labels

```yaml
CUBICLE_MENU:
  notebook: "📓 Notebook"
  laptop: "💻 Laptop"
  gizmo: "◉ Pos.Aya"
  stand_up: "⬆ Levantarse"
  stuff_box_status: "📦 Stuff Box"
  review: "⚠ Review"
```

HUMAN_COMMENT:

## 7.4 Achievement hooks

```yaml
ACHIEVEMENT_HOOKS:
  Cubicle_Awareness:
    trigger: player_stands_up_and_returns
    popup: "★ Cubicle Awareness — El cuerpo también cuenta."
```

HUMAN_COMMENT:

---

# 8. Screen G — Notebook / Somero entry

## 8.1 Screen goal

AUTO_FILL:

Show player identity, items, stage, achievements, and energy state. This is the memory/ledger layer without external memory.

AUTO_COMMENT: Notebook/Somero becomes the player’s continuity anchor.

HUMAN_COMMENT:

## 8.2 Exact screen text

```text
NOTEBOOK / SOMERO

Nombre: {PLAYER_NAME}
Capítulo: 1 — Cubicle Obedience
Stage: Orientation
Energía humana: estable
Energía gizmo: disponible
Items personales: guardados en Stuff Box
Somero Trace:
{PLAYER_NAME}-CH1-CUBICLE-STUFFBOX-STABLE

Nota:
La Corporation registra desempeño.
Somero recuerda contexto.
No son lo mismo.
```

AUTO_COMMENT: Clarifies Corporation tracking vs Somero memory. Important privacy/world distinction.

HUMAN_COMMENT:

## 8.3 Buttons

```yaml
BUTTONS:
  primary: VOLVER AL CUBÍCULO
  secondary: VER LOGROS
  optional: COPIAR SOMERO TRACE
```

HUMAN_COMMENT:

## 8.4 Achievement hook

```yaml
ACHIEVEMENT_HOOKS:
  First_Log:
    trigger: notebook_opened_first_time
    popup: "★ First Log — El contexto quedó escrito."
```

HUMAN_COMMENT:

---

# 9. Screen H — Laptop menu

## 9.1 Screen goal

AUTO_FILL:

Show first supervisor email, boss welcome message, first PR Worm nudge, goals, achievements. No full escalation yet.

AUTO_COMMENT: Laptop introduces corporate pressure in safe small doses.

HUMAN_COMMENT:

## 9.2 Laptop tabs

```yaml
LAPTOP_TABS:
  inbox: "📩 Inbox"
  goals: "🎯 Goals"
  achievements: "★ Achievements"
  systems: "⚙ Systems"
  app_future: "🔒 App Sync"
```

AUTO_COMMENT: App Sync appears locked/future, not active.

HUMAN_COMMENT:

## 9.3 Supervisor first email

```text
FROM: Supervisor Local
SUBJECT: Bienvenido, Trainee

Bienvenido al área operativa.
Hoy no necesitas resolver todo.
Solo necesitamos confirmar que puedes leer instrucciones, reconocer herramientas y volver a tu estación.

Paso 1: abre tu Notebook.
Paso 2: revisa este correo.
Paso 3: mantén disponibilidad.

La disponibilidad es la primera forma de productividad.
```

AUTO_COMMENT: “Mantén disponibilidad” seeds loop pressure while still looking normal.

HUMAN_COMMENT:

## 9.4 Boss welcome message

```text
FROM: Chief Office
SUBJECT: Tu oportunidad en la Corporation

Nos alegra tenerte en HUMAN in the LOOP.
Aquí cada acción cuenta.
Cada corrección cuenta.
Cada segundo disponible puede convertirse en valor.

No estás aquí para hacer trabajo pequeño.
Estás aquí para aprender a supervisar sistemas que todavía necesitan humanos.
```

AUTO_COMMENT: Prepares trainee supervisor role and corporate ideology.

HUMAN_COMMENT:

## 9.5 PR Worm first harmless nudge

```text
FROM: PR_Worm Service
SUBJECT: Small productivity reminder

Hola, Human.
Un recordatorio amistoso:
los loops funcionan mejor cuando nadie se sale antes de tiempo.

No es presión.
Es continuidad.
```

AUTO_COMMENT: First PR Worm message is humorous/suspicious but not yet hostile.

HUMAN_COMMENT:

## 9.6 Achievement hooks

```yaml
ACHIEVEMENT_HOOKS:
  First_Order:
    trigger: supervisor_email_read
    popup: "★ First Order — La primera instrucción fue recibida."
  Corporate_Welcome:
    trigger: boss_message_read
    popup: "★ Corporate Welcome — La oportunidad te encontró."
```

HUMAN_COMMENT:

---

# 10. Screen I — Pos.Aya first hint

## 10.1 Screen goal

AUTO_FILL:

Introduce Pos.Aya as a useful corporate tool with one soft anomaly: it remembers the location of personal items.

AUTO_COMMENT: Avoid full folded reveal. Just seed curiosity.

HUMAN_COMMENT:

## 10.2 Exact screen text

```text
◉ POS.AYA
Corporate routing assistant online.

Función inicial:
- recordar rutas
- mostrar contexto
- ayudarte a no perderte en procesos simples

Hint:
Tus pertenencias están en Stuff Box.
Puedo recordar esa ubicación si tú decides volver por ellas.
```

AUTO_COMMENT: “Si tú decides volver por ellas” gives agency and foreshadows item retrieval.

HUMAN_COMMENT:

## 10.3 Dialogue box

```yaml
DIALOGUE_BOX:
  speaker: Pos.Aya
  line: "No todo lo guardado queda perdido. Algunas rutas solo esperan permiso."
  player_options:
    - "Gracias."
    - "¿Rutas?"
    - "Solo dime qué sigue."
```

AUTO_COMMENT: Options allow warm, curious, or active-player response.

HUMAN_COMMENT:

## 10.4 Achievement hook

```yaml
ACHIEVEMENT_HOOKS:
  Gizmo_Handshake:
    trigger: pos_aya_hint_opened
    popup: "★ Gizmo Handshake — Pos.Aya recuerda una ruta."
```

HUMAN_COMMENT:

---

# 11. Screen J — Recovery choice seed

## 11.1 Screen goal

AUTO_FILL:

Introduce recovery as an option before fatigue. It should not feel like punishment or health lesson. It is a tiny RPG affordance.

AUTO_COMMENT: This is essential to make recovery playable later.

HUMAN_COMMENT:

## 11.2 Exact screen text

```text
MICROPAUSA DISPONIBLE

Antes de iniciar trabajo físico, puedes elegir una preparación breve.
No aumenta productividad inmediata.
Puede mejorar tu estado.

Opciones:
📖 Leer una línea
🌬 Respirar
🧍 Estirar
👔 Revisar uniforme
```

AUTO_COMMENT: “No aumenta productividad inmediata” is satire and mechanical promise.

HUMAN_COMMENT:

## 11.3 Buttons

```yaml
RECOVERY_BUTTONS:
  read: "📖 Leer"
  breathe: "🌬 Respirar"
  stretch: "🧍 Estirar"
  uniform: "👔 Revisar uniforme"
  skip: "Seguir trabajando"
```

HUMAN_COMMENT:

## 11.4 State hooks

```yaml
STATE_HOOKS:
  recovery_seed_seen: true
  energy_state: stable
  future_unlocks:
    - remove_uniform_later
    - read_recovery
    - meditate_recovery
    - movement_recovery
```

HUMAN_COMMENT:

---

# 12. Screen K — Review report

## 12.1 Screen goal

AUTO_FILL:

Allow the human tester to report what worked. The report is inert text. It does not modify repo/runtime.

AUTO_COMMENT: This preserves safe feedback loop.

HUMAN_COMMENT:

## 12.2 Exact screen text

```text
C6B REVIEW

Marca lo que pudiste revisar.
Este reporte no cambia el juego automáticamente.
Sirve para preparar la siguiente propuesta.
```

HUMAN_COMMENT:

## 12.3 Review fields

```yaml
REVIEW_FIELDS:
  abre: yes_no_partial
  intro: yes_no_partial
  application: yes_no_partial
  avatar: yes_no_partial
  items: yes_no_partial
  stuffbox: yes_no_partial
  cubicle: yes_no_partial
  notebook: yes_no_partial
  laptop: yes_no_partial
  supervisor_email: yes_no_partial
  boss_message: yes_no_partial
  PR_Worm_nudge: yes_no_partial
  Pos_Aya_hint: yes_no_partial
  recovery_seed: yes_no_partial
  stand_up: yes_no_partial
  problem: free_text
  next_interaction_request: free_text
```

HUMAN_COMMENT:

---

# 13. Achievement and badge trigger table

```yaml
TRIGGERS:
  achievements:
    First_Application:
      trigger: apply_pressed
      popup: "★ First Application — Entraste al proceso."
    Identity_Seed:
      trigger: name_and_avatar_saved
      popup: "★ Identity Seed — La silueta fue registrada."
    Stuff_Box_Ready:
      trigger: locker_closed_after_item_storage
      popup: "★ Stuff Box Ready — Tus pertenencias esperan."
    First_Log:
      trigger: notebook_opened
      popup: "★ First Log — El contexto quedó escrito."
    First_Order:
      trigger: supervisor_email_read
      popup: "★ First Order — La primera instrucción fue recibida."
    Corporate_Welcome:
      trigger: boss_message_read
      popup: "★ Corporate Welcome — La oportunidad te encontró."
    Cubicle_Awareness:
      trigger: stand_up_and_return
      popup: "★ Cubicle Awareness — El cuerpo también cuenta."
    Gizmo_Handshake:
      trigger: pos_aya_hint_opened
      popup: "★ Gizmo Handshake — Pos.Aya recuerda una ruta."

  badges:
    Early_Identity_Badge:
      trigger: inspect_avatar_before_continue
      popup: "◆ Early Identity — Miraste antes de obedecer."
    Personal_Meaning_Badge:
      trigger: all_core_items_selected
      popup: "◆ Personal Meaning — Guardaste más que herramientas."
    Before_Asked_Badge:
      trigger: open_notebook_or_laptop_before_prompt
      popup: "◆ Before Asked — Hiciste el paso antes de la orden."
    Efficient_Orientation_Badge:
      trigger: all_orientation_steps_under_target_time
      popup: "◆ Efficient Orientation — Te orientaste sin perder el hilo."
```

AUTO_COMMENT: These hooks are intentionally simple. They can be implemented with a plain JS state object.

HUMAN_COMMENT:

---

# 14. Low-processor implementation notes for later build

```yaml
LOW_PROCESSOR_IMPLEMENTATION:
  C6B_should_use:
    - static_HTML_sections
    - hash_or_state_navigation
    - simple_button_events
    - one_state_object
    - localStorage_optional_for_review_only
    - no_external_dependencies
    - no_accounts
    - no_payments
    - no_runtime_mutation
  screen_flow_should_work_even_if_minimal_JS:
    - core_sections_can_be_anchor_linked
    - primary_buttons_can_set_state_and_jump_to_section
```

AUTO_COMMENT: This prevents repeating the buttons-not-functional error. Core flow should degrade to anchor links if needed.

HUMAN_COMMENT:

---

# 15. Human approval checklist

```yaml
HUMAN_APPROVAL_CHECKLIST:
  accept_texts:
    - yes
    - no_revision_needed
  accept_PR_Worm_first_nudge:
    - yes
    - revise
    - remove_from_C6B
  accept_Pos_Aya_hint:
    - yes
    - revise
    - add_more_mystery
  accept_recovery_seed:
    - yes
    - revise
    - postpone
  accept_icons:
    - yes
    - revise_to_custom_style_later
  approve_for_build:
    - approve_C6B_minimal_playable_web_build
```

HUMAN_COMMENT:

---

# 16. Next artifact after approval

```yaml
NEXT_AFTER_APPROVAL:
  artifact: C6B_MINIMAL_PLAYABLE_WEB_BUILD
  route: GitHub_Pages
  status_label: ready_for_human_test_not_playable_confirmed
  required_review_before_link:
    - intro_button_works
    - application_flow_works
    - avatar_flow_works
    - item_selection_works
    - Stuff_Box_close_reaches_cubicle
    - notebook_opens
    - laptop_opens
    - Pos_Aya_hint_opens
    - recovery_seed_visible
    - review_report_visible
```

AUTO_COMMENT: The next build can only be called ready_for_human_test until the user confirms it runs on their device.

HUMAN_COMMENT:
