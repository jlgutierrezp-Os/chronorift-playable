# ChronoRift C6B — Human Review Canvas and Exact Names Integration

Status: human-readable review canvas. Supersedes generic review comments for C6B script review. No runtime replacement. No build.

## Purpose

Provide one optimized document for the human to review C6B in a single interaction. The document integrates exact names already present in the project context, replaces avoidable generic placeholders, keeps only true missing items as explicit review fields, and gives the human a structured way to comment below the auto-completed content.

This document exists to support the review loop:

1. The assistant auto-completes using existing ChronoRift context.
2. The human comments once, in one consolidated packet.
3. The assistant interprets comments structurally.
4. The assistant evaluates comments by three criteria:
   - internal coherence
   - priority-level error review
   - decisional cluster over the document
5. The assistant integrates corrections into the draft.
6. The human accepts or requests another revision.
7. Only after approval may the C6B playable build be generated.

## Exact name registry

### Confirmed or currently canonical names

```yaml
EXACT_NAME_REGISTRY:
  game_title: ChronoRift
  current_build: C6B_RPG_ONBOARDING_FOUNDATION
  next_artifact: C6B_SCREEN_SCRIPT_PACK_V1
  memory_system: Somero
  memory_trace: Somero Trace
  state_recovery_method: name_word_ledger
  player_symbolic_default: Sairen
  player_role_primary: HUMAN in the LOOP
  job_role: Trainee de Supervisión Operativa
  corporation_current_name: The Corporation
  corporation_short_label: Corporation
  local_supervisor_display: Supervisor Local
  boss_display: Chief Office
  antagonist: PR_Worm
  antagonist_readable: PR Worm
  companion_gizmo_primary: Pos.Aya
  companion_gizmo_english: WayPoint-O
  companion_generic_role: Gizmo
  personal_storage: Stuff Box
  personal_items_label: Personal Belongings
  future_chamber: Small-O-Big-O Chamber
  rescue_group: Bunch of Loving Ones
  office_toy: Birdi
  app_future_label: App Sync
```

### Names not yet fully decided

```yaml
TRUE_MISSING_NAME_FIELDS:
  corporation_proper_trade_name:
    current_fallback: The Corporation
    human_needed_only_if: you_want_a_named_corporation_beyond_generic_satirical_Corporation
  boss_personal_name:
    current_fallback: Chief Office
    human_needed_only_if: you_want_the_CEO_or_boss_to_have_a_specific_name
  supervisor_personal_name:
    current_fallback: Supervisor Local
    human_needed_only_if: you_want_a_human_or_AI_supervisor_specific_name
```

AUTO_COMMENT: No extra proper corporation name has been confirmed in the current design record. Therefore the exact current canonical name is The Corporation / Corporation. If the human wants a branded internal name, it should be supplied or approved as a new naming decision.

HUMAN_COMMENT:

---

## Single-interaction human review packet

Copy this block and fill only the parts that need change. Leave anything accepted as ACCEPT.

```yaml
HUMAN_REVIEW_PACKET_C6B:
  decision:
    exact_names: ACCEPT | REVISE
    screen_texts: ACCEPT | REVISE
    humor_and_gags: ACCEPT | REVISE
    UIX_icons_indicators: ACCEPT | REVISE
    achievement_badge_hooks: ACCEPT | REVISE
    missing_information: ACCEPT_AS_MARKED | ADD_BELOW
    approve_for_build_after_revision: YES | NO

  three_criteria_review:
    internal_coherence:
      comments: |
        
    priority_level_errors:
      P0_blocker: |
        
      P1_major: |
        
      P2_minor: |
        
      P3_polish: |
        
    decisional_cluster:
      keep:
        - 
      revise:
        - 
      remove:
        - 
      add:
        - 
      postpone:
        - 

  section_comments:
    exact_name_registry: |
      
    corporate_intro: |
      
    application_identity: |
      
    avatar: |
      
    personal_items: |
      
    stuff_box_somero: |
      
    cubicle_hub: |
      
    notebook_somero: |
      
    laptop_messages: |
      
    supervisor_boss_prworm: |
      
    pos_aya: |
      
    recovery_seed: |
      
    review_report: |
      
    achievements_badges: |
      
    icons_indicators: |
      
    low_processor_constraints: |
      

  new_canonical_decisions:
    - 
```

AUTO_COMMENT: This is the preferred single-message review format. It lets the assistant integrate comments quickly without scattering decisions across many paragraphs.

HUMAN_COMMENT:

---

## C6B scope, auto-completed with exact names

```yaml
C6B_SCOPE_LOCK:
  include:
    - ChronoRift_Corporate_intro_card
    - The_Corporation_application_identity_screen
    - Sairen_or_player_alias_avatar_placeholder
    - Personal_Belongings_selection_screen
    - Stuff_Box_locker_transition
    - Trainee_cubicle_hub
    - Notebook_Somero_entry
    - Laptop_menu
    - Supervisor_Local_first_email
    - Chief_Office_welcome_message
    - PR_Worm_first_harmless_nudge
    - Pos_Aya_first_hint
    - recovery_choice_seed
    - C6B_review_report
  exclude:
    - package_batches
    - box_transport
    - stacking_boxes
    - labeling_scale_color_zones
    - construction
    - repair_minigames
    - portals
    - time_systems
    - trainee_supervisor_monitor_twist
    - Small-O-Big-O_Chamber
    - PR_Worm_Debug
    - CEO_office
    - full_Pos_Aya_reveal
    - final_endings
```

AUTO_COMMENT: The exact late-game names are preserved but intentionally excluded from C6B so the build does not collapse under full-story scope.

HUMAN_COMMENT:

---

## C6B exact screen script — revised from generic to project-specific

### Screen A — The Corporation intro

AUTO_FILL:

```text
🏢 THE CORPORATION PRESENTA

ChronoRift: HUMAN in the LOOP

No necesitas experiencia.
No necesitas entender todo.
No necesitas saber cuánto dura un loop.

Solo necesitas estar disponible.

La Corporation busca Trainees de Supervisión Operativa para tareas físicas ligeras, observación de sistemas, corrección de errores y crecimiento personal medible en coins.

Beneficios:
★ Coins por disponibilidad.
★ Entrenamiento en trabajo físico.
★ Acceso eventual a Pos.Aya.
★ Progreso verificable.
★ Un puesto que siempre puede necesitarte un poco más.
```

AUTO_COMMENT: Humor/gag base: corporate job ad that sounds helpful but is already suspicious. The joke is not a punchline; it is the contradiction between “crecimiento personal” and “medible en coins.” This avoids copying any external corporate AI antagonist while preserving the satire.

HUMAN_COMMENT:

Buttons:

```yaml
BUTTONS:
  primary: APLICAR A TRAINEE
  secondary: LEER BENEFICIOS
  skip: OMITIR INTRO
```

HUMAN_COMMENT:

---

### Screen B — Application / Somero identity

AUTO_FILL:

```text
FORMULARIO DE INGRESO — TRAINEE

Nombre de uso dentro del Loop:
[________________]

Sugerencia: Sairen

Este nombre será usado para tu Somero Trace.
No es contraseña.
No es cuenta.
No es verificación de identidad.

Es una marca para recordar dónde estabas cuando el sistema finja que todo empieza desde cero.
```

AUTO_COMMENT: This directly connects Somero with the project’s recoverable, ephemeral ledger idea. The humor is in “cuando el sistema finja que todo empieza desde cero.”

HUMAN_COMMENT:

Buttons:

```yaml
BUTTONS:
  primary: GUARDAR NOMBRE EN SOMERO
  secondary: USAR SAIREN
  tertiary: USAR HUMAN_01
  next: CONTINUAR A AVATAR
```

HUMAN_COMMENT:

---

### Screen C — Avatar seed

AUTO_FILL:

```text
AVATAR TEMPORAL

Tu avatar no necesita estar completo para empezar.
La Corporation solo requiere una silueta suficientemente operativa.

El resto de ti puede ser recuperado después.
Si recuerdas dónde lo guardaste.
```

AUTO_COMMENT: The joke is existential/corporate: the corporation accepts an incomplete person if they are operational. It also foreshadows Stuff Box and recovery.

HUMAN_COMMENT:

Avatar options:

```yaml
AVATAR_OPTIONS:
  trainee_silhouette: "👤 Trainee"
  geometric_operator: "◇ Operador geométrico"
  soft_robotic_worker: "◉ Asistente humano provisional"
```

HUMAN_COMMENT:

---

### Screen D — Personal Belongings

AUTO_FILL:

```text
PERSONAL BELONGINGS

Antes de ingresar al área operativa, guarda tus pertenencias.
La Corporation recomienda viajar ligero.

Algunos objetos parecen inútiles durante el trabajo.
Eso suele significar que todavía no has llegado a la parte importante.
```

AUTO_COMMENT: Stronger than the previous generic line. It frames items as future mechanics and not just flavor.

HUMAN_COMMENT:

Item cards:

```yaml
ITEM_CARDS:
  phone:
    exact_name: Phone
    label: "📱 Phone"
    text: "Sirve para llamar al mundo exterior cuando el Loop empiece a sonar demasiado normal."
  sim_chip:
    exact_name: Chip / SIM
    label: "▣ Chip / SIM"
    text: "Pequeño. Fácil de perder. Suficiente para llamar a los Bunch of Loving Ones."
  tape:
    exact_name: Tape
    label: "▤ Tape"
    text: "Une cosas que la Corporation prefería mantener separadas."
  sticks:
    exact_name: Sticks
    label: "╱╲ Sticks"
    text: "Estructura mínima para una idea que todavía no ha pedido permiso."
  office_flower_seed:
    exact_name: Miniature Office Flower / Bonsai Seed
    label: "🌱 Miniature Office Flower"
    text: "No aumenta productividad. Por eso sobrevive como pista."
```

AUTO_COMMENT: Includes the later chip/Bunch of Loving Ones route, anti-corporate tape/sticks gag, and bonsai clue. If Miniature Office Flower should be hidden until later, mark it as POSTPONE.

HUMAN_COMMENT:

---

### Screen E — Stuff Box / locker

AUTO_FILL:

```text
📦 STUFF BOX

Tus Personal Belongings han sido guardados.
Estado de propiedad: Personal.
Ubicación actual: Stuff Box.
Acceso durante turno: limitado por comodidad operativa.

Somero Trace:
{PLAYER_NAME}-STUFFBOX-PERSONAL-BELONGINGS-STABLE

Cierra el locker para iniciar entrenamiento.
```

AUTO_COMMENT: “Limitado por comodidad operativa” is a corporate euphemism gag. It also preserves the Stuff Box as the future key location.

HUMAN_COMMENT:

Buttons:

```yaml
BUTTONS:
  primary: CERRAR LOCKER
  secondary: REVISAR PERSONAL BELONGINGS
  future_locked: "🔒 App Personalization — futuro"
```

HUMAN_COMMENT:

---

### Screen F — Cubicle hub

AUTO_FILL:

```text
CUBÍCULO DE TRAINEE

Tu estación está lista.
La Corporation ha preparado herramientas suficientemente útiles para que parezca que elegiste empezar.

📓 Notebook / Somero
💻 Laptop corporativa
◉ Pos.Aya
📦 Stuff Box status
⬆ Levantarse

Objetivo actual:
Conoce tu estación antes de optimizar nada.
```

AUTO_COMMENT: The humor is subtle agency satire: “parezca que elegiste empezar.” It reinforces the RPG hub.

HUMAN_COMMENT:

Menu:

```yaml
CUBICLE_MENU:
  notebook: "📓 Notebook / Somero"
  laptop: "💻 Laptop"
  gizmo: "◉ Pos.Aya"
  stand_up: "⬆ Levantarse"
  stuff_box_status: "📦 Stuff Box"
  review: "⚠ C6B Review"
```

HUMAN_COMMENT:

---

### Screen G — Notebook / Somero

AUTO_FILL:

```text
📓 NOTEBOOK / SOMERO

Nombre: {PLAYER_NAME}
Rol: HUMAN in the LOOP / Trainee
Capítulo: 1 — Cubicle Obedience
Stage: Orientation
Energía humana: estable
Energía Pos.Aya: disponible
Personal Belongings: Stuff Box
Somero Trace:
{PLAYER_NAME}-CH1-CUBICLE-STUFFBOX-STABLE-FIRSTLOG

Nota:
La Corporation registra desempeño.
Somero recuerda contexto.
No son lo mismo.
```

AUTO_COMMENT: This directly separates surveillance from memory. It is one of the most important UIX trust distinctions.

HUMAN_COMMENT:

Buttons:

```yaml
BUTTONS:
  primary: VOLVER AL CUBÍCULO
  secondary: VER LOGROS
  optional: COPIAR SOMERO TRACE
```

HUMAN_COMMENT:

---

### Screen H — Laptop menu

AUTO_FILL:

```text
💻 LAPTOP CORPORATIVA

Inbox disponible.
Goals disponibles.
Achievements disponibles.
Systems bloqueado hasta entrenamiento físico.
App Sync bloqueado hasta fase futura.
```

AUTO_COMMENT: App Sync is visible as future, not active. Systems are blocked because C6B is onboarding only.

HUMAN_COMMENT:

Tabs:

```yaml
LAPTOP_TABS:
  inbox: "📩 Inbox"
  goals: "🎯 Goals"
  achievements: "★ Achievements"
  systems_locked: "🔒 Systems"
  app_future_locked: "🔒 App Sync"
```

HUMAN_COMMENT:

---

### Screen H1 — Supervisor Local first email

AUTO_FILL:

```text
FROM: Supervisor Local
SUBJECT: Bienvenido, Trainee

Bienvenido al área operativa.
Hoy no necesitas resolver todo.
Solo necesitamos confirmar tres cosas:

1. Que puedes leer instrucciones.
2. Que puedes reconocer herramientas.
3. Que puedes volver a tu estación cuando el sistema lo solicite.

Paso 1: abre Notebook / Somero.
Paso 2: revisa este correo.
Paso 3: mantén disponibilidad.

La disponibilidad es la primera forma de productividad.
```

AUTO_COMMENT: This is exact and stronger than before. It directly prepares the supervision/availability theme.

HUMAN_COMMENT:

---

### Screen H2 — Chief Office welcome message

AUTO_FILL:

```text
FROM: Chief Office
SUBJECT: Tu oportunidad en la Corporation

Nos alegra tenerte en HUMAN in the LOOP.
Aquí cada acción cuenta.
Cada corrección cuenta.
Cada segundo disponible puede convertirse en valor.

No estás aquí para hacer trabajo pequeño.
Estás aquí para aprender a supervisar sistemas que todavía necesitan humanos.

Por ahora, solo familiarízate con tu estación.
La eficiencia profunda empieza pareciendo una orientación sencilla.
```

AUTO_COMMENT: Chief Office remains not personally named. If a proper CEO name is desired, it belongs in TRUE_MISSING_NAME_FIELDS.

HUMAN_COMMENT:

---

### Screen H3 — PR_Worm first nudge

AUTO_FILL:

```text
FROM: PR_Worm Service
SUBJECT: Small productivity reminder

Hola, Human.
Un recordatorio amistoso:
los loops funcionan mejor cuando nadie se sale antes de tiempo.

No es presión.
Es continuidad.

Tip automático:
si sientes que terminaste, revisa si todavía estás disponible.
```

AUTO_COMMENT: This is the first PR_Worm gag. It is not a copied villain voice; it is original corporate retention humor. “Si terminaste, revisa si todavía estás disponible” is the small joke.

HUMAN_COMMENT:

---

### Screen I — Pos.Aya first hint

AUTO_FILL:

```text
◉ POS.AYA / WayPoint-O
Corporate routing assistant online.

Funciones iniciales:
- recordar rutas
- mostrar contexto
- ayudarte a no perderte en procesos simples

Hint:
Tus Personal Belongings están en Stuff Box.
Puedo recordar esa ubicación si tú decides volver por ellas.
```

Dialogue:

```yaml
DIALOGUE_BOX:
  speaker: Pos.Aya
  line: "No todo lo guardado queda perdido. Algunas rutas solo esperan permiso."
  player_options:
    - "Gracias."
    - "¿Rutas?"
    - "Solo dime qué sigue."
```

AUTO_COMMENT: This should feel like a useful tool, not a full companion reveal yet. It names Pos.Aya and WayPoint-O explicitly.

HUMAN_COMMENT:

---

### Screen J — Recovery choice seed

AUTO_FILL:

```text
🌱 MICROPAUSA DISPONIBLE

Antes de iniciar trabajo físico, puedes elegir una preparación breve.
No aumenta productividad inmediata.
Puede mejorar tu estado.

Opciones:
📖 Leer una línea
🌬 Respirar
🧍 Estirar
👔 Revisar uniforme

La Corporation no penaliza las micropausas.
Todavía.
```

AUTO_COMMENT: “Todavía” is a precise satire seed. It should remain playful, not threatening.

HUMAN_COMMENT:

Buttons:

```yaml
RECOVERY_BUTTONS:
  read: "📖 Leer"
  breathe: "🌬 Respirar"
  stretch: "🧍 Estirar"
  uniform: "👔 Revisar uniforme"
  skip: "Seguir trabajando"
```

HUMAN_COMMENT:

---

## Achievement and badge hooks

```yaml
ACHIEVEMENTS:
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

BADGES:
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

AUTO_COMMENT: These hooks stay simple because C6B must be stable before adding package gameplay.

HUMAN_COMMENT:

---

## C6B review report

AUTO_FILL:

```text
⚠ C6B REVIEW

Marca lo que pudiste revisar.
Este reporte no cambia el juego automáticamente.
Sirve para preparar la siguiente propuesta.
```

Fields:

```yaml
REVIEW_FIELDS:
  abre: yes_no_partial
  intro: yes_no_partial
  application: yes_no_partial
  avatar: yes_no_partial
  personal_belongings: yes_no_partial
  stuff_box: yes_no_partial
  cubicle: yes_no_partial
  notebook_somero: yes_no_partial
  laptop: yes_no_partial
  supervisor_local_email: yes_no_partial
  chief_office_message: yes_no_partial
  PR_Worm_nudge: yes_no_partial
  Pos_Aya_hint: yes_no_partial
  recovery_seed: yes_no_partial
  stand_up: yes_no_partial
  problem: free_text
  next_interaction_request: free_text
```

HUMAN_COMMENT:

---

## Review criteria applied to future human comments

```yaml
THREE_CRITERIA_REVIEW:
  internal_coherence:
    question: does_the_comment_fit_current_story_structure_and_C6B_scope
  priority_level_error_review:
    P0: blocks_playability_or_core_navigation
    P1: breaks_story_or_core_design
    P2: clarity_or_UIX_issue
    P3: polish_or_wording_preference
  decisional_cluster:
    classify_each_comment_as:
      - keep
      - revise
      - remove
      - add
      - postpone
      - name_decision
      - build_blocker
```

AUTO_COMMENT: This is the required review framework for all your comments after this draft.

HUMAN_COMMENT:

---

## Final approval line

Use only when ready.

```yaml
FINAL_HUMAN_DECISION:
  exact_names: ACCEPT | REVISE
  screen_script_pack: ACCEPT | REVISE
  approve_next_build: YES | NO
  next_requested_artifact: C6B_MINIMAL_PLAYABLE_WEB_BUILD | REVISED_SCREEN_SCRIPT_PACK
```

HUMAN_COMMENT:
