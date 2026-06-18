# CHRONORIFT_SERIOUS_DEVELOPMENT_PROGRAM_V1

Status: approval packet. No runtime replacement.

## Purpose

Define a serious development program for ChronoRift as a narrative RPG, cinematic onboarding, logistics builder, package/farm-style progression, and modular construction game.

This document must be approved before the next gameplay interaction or next build candidate.

## Product identity

ChronoRift is not only a portal-box prototype. It is a structured game with these layers:

- RPG story progression
- cinematic storytelling
- dialogue and action choices
- personal item storage
- package and warehouse logistics
- modular construction in a 20 x 20 x 20 workspace
- farm-style improvement loop
- Roblox-like build affordances inside a constrained workspace
- player feedback to issue/update pipeline

## Core development rule

Build the game in serious vertical slices. Do not add complex physics, boxes, portals, or construction before the RPG onboarding and cubicle loop are functional.

## Required core systems

### 1. Cinematic story system

Purpose: tell story moments using short scene sequences.

Minimum features:

- intro cinematic
- corporate recruitment ad
- email or work-network message
- job application acceptance
- transition into avatar and Stuff Box
- later PR Worm cinematic events

Acceptance:

- scene can advance step by step
- text and visual panel are readable
- no game-breaking dependency on heavy animation

### 2. RPG dialogue system

Purpose: conduct story and decisions.

Minimum features:

- dialogue box
- speaker label
- next button
- choices
- flags from choices
- achievement-triggered dialogue

Acceptance:

- dialogue can advance
- choices modify a local state flag
- achievements can trigger new dialogue

### 3. Action menu system

Purpose: each object, surface, area, and package exposes contextual actions.

Targets:

- floor
- wall
- ceiling
- desk
- laptop
- notebook
- locker
- Stuff Box
- box
- package
- block
- portal surface
- jam area
- printer

Acceptance:

- action menu appears for selected target
- only relevant actions appear
- action result is logged

### 4. Inventory and item storage system

Purpose: track player items, personal items, story items, and storage.

Storage types:

- player carry inventory
- Stuff Box
- desk storage
- package contents
- lost or stolen item state
- supervisor-owned item state

Acceptance:

- item can move between owner states
- notebook can display item ownership
- personal items can be referenced by story flags

### 5. Player personal item system

Initial personal items:

- phone
- phone chip / SIM
- adhesive tape
- sticks

Rules:

- items are not cosmetic only
- items can support story endings
- items can combine in RPG scenes
- item ownership can change after PR Worm event

### 6. Package and box system

Purpose: support packages, boxes, labels, and shipping loops.

Types:

- personal package
- work package
- delivery box
- stuck box
- stackable box
- special labeled box

Acceptance:

- package has label/type/state
- box can be visible in world
- future builds can grab and stack boxes

### 7. Cubicle hub system

Purpose: first stable playable hub.

Interactables:

- notebook / Somero log
- laptop
- Stuff Box reference
- desk toys
- delivery area
- stand up transition

Acceptance:

- player can navigate cubicle screens
- notebook and laptop are reachable
- Stuff Box continuity is visible

### 8. Laptop application system

Purpose: in-world UI for messages, goals, 3D printing, and mini-games.

Apps:

- messages
- goals
- achievements
- printer
- minigame launcher
- delivery request
- Somero summary

Acceptance:

- laptop menu opens
- app buttons work
- one message and one goal are visible

### 9. 3D printer and block request system

Purpose: allow player to request blocks for construction and mini-games.

Block classes:

- scaffold
- conveyor XY
- conveyor YX
- elevator up
- elevator down
- piston six-axis
- angle guide
- slide
- trampoline
- receiving net

Acceptance:

- block list appears
- print request can be selected
- print sequence appears
- block appears in printer output zone

### 10. Workspace 20 x 20 x 20 system

Purpose: main construction and logistics playfield.

Contract:

- workspace size: 20 x 20 x 20
- each cell can hold up to 4 boxes
- each cell can hold one portal or portal surface
- build on floor, walls, and ceiling
- support modular construction like a constrained Roblox-like build zone

Acceptance for early builds:

- workspace preview exists
- cells are conceptually represented
- floor/wall/ceiling build categories exist

### 11. Farm-style progression loop

Purpose: create repeated satisfying work cycles.

Loop:

1. receive task
2. inspect package or area
3. choose tool/block/action
4. repair, sort, ship, or build
5. gain coins, achievement, story flag, or unlock
6. return to notebook/laptop for next task

Acceptance:

- one task can be completed
- reward is visible
- next task becomes available

### 12. Mini-game system

Purpose: represent repairs, jams, routing, and special logistics tasks.

Examples:

- jam clear runner
- slide/chute runner
- horizontal distribution
- vertical lift route
- portal surface calibration
- service repair challenge

Acceptance:

- minigame can start from area menu or laptop
- minigame has win/fail condition
- win updates main world state

### 13. Feedback to issue/update pipeline

Purpose: allow player feedback to improve the game without public write access.

Flow:

1. player plays
2. player submits inert feedback text
3. human brings feedback to /agent-luu or /agent-apply
4. agent classifies bug/feature/design issue
5. agent creates or updates issue/review doc
6. agent proposes update
7. human approves before next gameplay interaction

Acceptance:

- feedback is plain text
- no public user can modify repository
- no public agent command is executed
- updates are presented for approval

## Development phases

### Phase 0. Governance and pipeline hardening

Deliverables:

- secure semiautomated development rules
- no-go registry
- delivery route gate
- functional review checklist

Exit criteria:

- GitHub Pages route is confirmed usable
- no sandbox/local external-file route is used for handoff

### Phase 1. RPG onboarding vertical slice

Deliverables:

- intro
- application
- avatar placeholder
- personal item selection
- Stuff Box close to Stage 1

Exit criteria:

- all screen navigation works on target device

### Phase 2. Cubicle hub vertical slice

Deliverables:

- notebook
- laptop
- desk props
- delivery area
- stand up room view

Exit criteria:

- player can navigate core cubicle interactions

### Phase 3. Somero and item ownership

Deliverables:

- Somero summary
- item ownership registry
- notebook recovery view

Exit criteria:

- player can see recoverable state

### Phase 4. Package and box reintroduction

Deliverables:

- visible boxes
- packages with labels
- grab/release
- stack two boxes
- carry one/two boxes by unlock state

Exit criteria:

- boxes visible and interactable without no-clip failures

### Phase 5. Workspace construction subset

Deliverables:

- 20 x 20 x 20 workspace preview
- cell contract
- build on floor/wall/ceiling categories
- first printed block

Exit criteria:

- player can print one block and place or inspect it

### Phase 6. Logistics and farm loop

Deliverables:

- receive task
- inspect package
- choose action
- complete shipping/repair/classification task
- coins/achievement/story flag

Exit criteria:

- one repeated work loop is fun and understandable

### Phase 7. Minigames

Deliverables:

- first jam clear runner
- reward returns to main world
- cleared area updates

Exit criteria:

- minigame affects main world state

### Phase 8. Portals and calculated physics

Deliverables:

- portal surfaces
- calculated box transport
- deterministic slide/conveyor/elevator effects

Exit criteria:

- portal and movement effects are predictable and testable

## Release gates

A build may be handed to the human only if:

- route is GitHub Pages or confirmed working route
- primary navigation works
- required screen sequence works
- review packet is visible
- known failed route is not repeated
- no core runtime replacement occurred without approval

## Approval request

Approve this program before the next game build if the direction is correct.

Proposed next build after approval:

C6B_RPG_ONBOARDING_VERTICAL_SLICE
