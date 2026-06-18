# CHRONORIFT_C6B_RPG_ONBOARDING_FOUNDATION_PROPOSAL_V1

Status: approval packet. No runtime replacement.

## Purpose

Define the exact C6B build proposal before gameplay implementation. This proposal uses the already described ChronoRift story, but limits implementation to the RPG onboarding foundation so navigation, story, identity, item storage, and first corporate pressure beats can stabilize before package logistics, construction, repair minigames, portals, or time systems are reintroduced.

## Build name

C6B_RPG_ONBOARDING_FOUNDATION

## Goals

- Transform C6 Onboarding Gate into a real RPG opening.
- Keep navigation stable.
- Introduce storytelling without heavy gameplay systems.
- Seed the Corporation, Supervisor, Boss, PR Worm, Pos.Aya, Somero, personal items, energy, and recovery choices.
- Preserve no-core-runtime-replacement boundary.

## Selected chapter/stage subset

### Chapter 0 partial: Recruitment and identity

Included stages:

- Stage 0.1: Recruitment intro.
- Stage 0.2: Job application.
- Stage 0.3: Avatar placeholder.
- Stage 0.4: Personal item selection.
- Stage 0.5: Stuff Box storage and locker close.

### Chapter 1 partial: Cubicle obedience

Included stages:

- Stage 1.1: Open Notebook.
- Stage 1.2: Open Laptop.
- Stage 1.3: Read supervisor first task.
- Stage 1.4: Read boss welcome message.
- Stage 1.5: Stand up from desk and return.
- Stage 1.6: Receive first Pos.Aya hint.
- Stage 1.7: Receive first harmless PR Worm productivity nudge.
- Stage 1.8: See first recovery choice seed.

## Screen proposal

### Screen A. Corporate intro card

Content:
- The Corporation recruits HUMAN in the LOOP workers.
- The ad says no experience is required.
- Tone is friendly, readable, and suspiciously permanent.

Player action:
- Apply.

### Screen B. Application and identity

Content:
- Player enters or confirms a name.
- The name is presented as a future Somero save anchor.

Player action:
- Continue to avatar.

### Screen C. Avatar placeholder

Content:
- Avatar options remain simple.
- Avatar is identity seed, not final customization.

Player action:
- Choose or inspect avatar.

### Screen D. Personal items

Included items:
- Phone.
- Phone chip / SIM.
- Tape.
- Sticks.
- Optional placeholder item.

Player action:
- Select items.

### Screen E. Stuff Box / locker

Content:
- Items are stored.
- Notebook/Somero note indicates item ownership: Stuff Box.
- Closing locker transitions to cubicle.

Player action:
- Close locker.

### Screen F. Cubicle hub

Content:
- Desk, notebook, laptop, Stuff Box reference, stand-up control.

Player actions:
- Open Notebook.
- Open Laptop.
- Stand up.
- Open Pos.Aya hint.

### Screen G. Notebook / Somero entry

Content:
- Player name.
- Avatar seed.
- Items stored.
- Stage: Cubicle onboarding.
- Achievements unlocked.
- Energy state: stable.

Player action:
- Return to cubicle.

### Screen H. Laptop menu

Content:
- Supervisor first email.
- Boss welcome message.
- PR Worm first harmless nudge.
- Goals tab.
- Achievements tab.

Player action:
- Read messages.

### Screen I. Pos.Aya first hint

Content:
- Pos.Aya appears as corporate productivity gizmo.
- It gives one helpful hint.
- It does not yet reveal folded agent origin.

Required hint function:
- It notices that personal items were stored and says it will remember their location.

### Screen J. Recovery choice seed

Content:
- The player sees a small prompt: read, breathe, stretch, or remove uniform later.
- This is only a seed, not full recovery system.

Player action:
- Mark choice or inspect option.

### Screen K. Review report

Content:
- Human tester can report if screens are reachable and whether story beats are visible.

## Exact achievements included

- First_Application: complete job application.
- Identity_Seed: choose name/avatar seed.
- Stuff_Box_Ready: store selected items.
- First_Log: open Notebook.
- First_Order: read supervisor first email.
- Corporate_Welcome: read boss message.
- Cubicle_Awareness: stand up and return.
- Gizmo_Handshake: open Pos.Aya or receive first hint.

## Exact badges included

- Early_Identity_Badge: inspect avatar or item meaning before prompt completion.
- Personal_Meaning_Badge: select all meaningful personal items before moving on.
- Before_Asked_Badge: perform a required interaction before the tutorial asks.
- Efficient_Orientation_Badge: complete all cubicle orientation steps under target time.

## PR Worm inclusion level

Included:
- one harmless productivity nudge.
- message tone: helpful, productivity-positive, slightly persistent.

Not included:
- manipulation.
- full loop-forever escalation.
- anti-rest pressure.
- infection mechanics.
- corruption of Pos.Aya.

## Pos.Aya inclusion level

Included:
- corporate productivity tool mask.
- first helpful hint.
- one soft anomaly seed: remembers item location.

Not included:
- full folded agent reveal.
- corporate origin reveal.
- PR Worm interaction with hidden layers.

## Excluded systems

Do not include in C6B:

- package batches.
- box transport.
- stack boxes.
- labels / scale / color zones.
- construction grid.
- repair minigames.
- portals.
- time systems.
- full PR Worm escalation.
- full Pos.Aya reveal.
- final endings.

## Test packet

Human test must verify:

- intro opens.
- apply screen reachable.
- avatar screen reachable.
- personal items screen reachable.
- Stuff Box screen reachable.
- locker close reaches cubicle.
- notebook opens.
- laptop opens.
- supervisor first email visible.
- boss welcome visible.
- PR Worm first nudge visible.
- Pos.Aya first hint visible.
- stand up and return works.
- recovery choice seed visible.
- review report visible.

## Human report format

```text
CHRONORIFT_C6B_RPG_ONBOARDING_REVIEW
abre:
intro:
application:
avatar:
items:
stuffbox:
cubicle:
notebook:
laptop:
supervisor_email:
boss_message:
PR_Worm_nudge:
Pos_Aya_hint:
stand_up:
recovery_seed:
review_report:
problema:
NEXT_INTERACTION_REQUEST:
```

## Safe point preserved

Preserve:

- C6 static navigation gate.
- GitHub Pages route only.
- No sandbox/local external-file handoff.
- No JavaScript-only navigation for core screen flow.
- No core runtime replacement.
- No package logistics before RPG onboarding passes.

## Approval gate

Approval required before implementation.

Options:

- approve_C6B_build
- revise_C6B_scope
- approve_without_PR_Worm_nudge
- approve_with_more_Pos_Aya
- hold_until_more_story_detail
