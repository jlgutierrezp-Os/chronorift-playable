# CHRONORIFT_SERIOUS_DEVELOPMENT_PROGRAM_V1

Status: proposed development program for human approval. No runtime replacement.

## Purpose

Define a serious, staged development program for ChronoRift as an office RPG, logistics-builder, package-routing, portal/time-puzzle, and life-purpose narrative game.

This document must be approved before the next large gameplay interaction is built.

## Core game identity

ChronoRift is not only a portal prototype. It is a structured game with:

- RPG story progression
- cinematic onboarding
- dialogue boxes
- action menus
- player avatar identity
- personal items
- item storage
- Stuff Box storage
- package boxes
- cubicle and office areas
- future cafeteria and warehouse areas
- 20 x 20 x 20 modular workspace
- farm-like progression loops
- Roblox-like modular construction affordances
- player feedback loop that generates issues and update proposals

## Development principles

1. Build stable screen flow before complex systems.
2. Recover RPG foundation before physics, boxes, portals, and construction.
3. Treat public player feedback as inert text.
4. Never allow public users or public agents to modify the repo.
5. Generate update proposals after feedback.
6. Present each update for human approval before the next gameplay interaction.
7. Prefer deterministic mathematical effects over heavy physical simulation when that improves agility and reliability.
8. Preserve every confirmed working feature as a safe point.

## Architecture layers

### Layer 1. Screen flow engine

Purpose: move through screens reliably without broken buttons.

Screens:
- intro cinematic
- application / identity
- avatar selection
- personal item selection
- Stuff Box / locker
- cubicle
- notebook
- laptop
- cubicle room view
- workspace preview
- review / feedback

Minimum rule: every screen must be reachable by a static route or reliable state transition.

### Layer 2. Cinematic storytelling engine

Purpose: tell story through simple animated sequences.

Capabilities:
- scene cards
- corporate ad panels
- email animation
- application sequence
- avatar onboarding
- locker close transition
- stage transition scenes

No copied assets, characters, or protected content. External references are mood references only.

### Layer 3. RPG dialogue engine

Purpose: guide story and choices through dialogue boxes.

Capabilities:
- dialogue box
- speaker name
- portrait or avatar marker
- choice list
- achievement-triggered dialogue
- supervisor and boss messages
- Pos.Aya / gizmo hints
- branch flags

### Layer 4. Action menu engine

Purpose: every relevant target exposes only appropriate actions.

Targets:
- floor
- wall
- ceiling
- desk
- laptop
- notebook
- locker
- Stuff Box
- personal item
- box
- package label
- block
- portal surface
- printer
- jammed area
- shipping lane

### Layer 5. Inventory and storage engine

Storage types:
- player inventory
- personal item registry
- Stuff Box storage
- desk storage
- laptop state
- package storage
- warehouse storage
- item ownership registry

Critical rule: track who has each important item.

### Layer 6. Somero recovery engine

Purpose: lightweight recovery without heavy database.

Payload categories:
- player name
- avatar id
- avatar features
- personal items
- current item ownership
- stage
- story flags
- achievements
- skills
- current area

Somero is not an authorization system and must not grant repo access, admin access, deployment access, or public write access.

### Layer 7. Area graph and world model

Areas:
- intro memory space
- Stuff Box / locker
- cubicle seated desk
- cubicle room
- personal delivery area
- cafeteria / comedor
- warehouse / bodega
- main work area
- 20 x 20 x 20 workspace

Transitions must be explicit and testable.

### Layer 8. Package and box system

Box types:
- personal package
- work package
- fragile package
- jammed package
- labeled package
- delivery goal package
- quest item package
- block supply package

Package boxes should integrate with story, logistics, and achievement progression.

### Layer 9. Modular construction system

Workspace contract:
- 20 x 20 x 20 cells
- floor, wall, and ceiling build surfaces
- up to 4 boxes per cell
- one portal per cell or surface rule
- blocks placeable as deterministic gameplay tools

Construction is inspired by modular building play, but must be original to ChronoRift and constrained by its logistics and story systems.

### Layer 10. Farm-like progression loop

Progression loops:
- receive package
- classify package
- repair routing
- build support system
- deliver / ship
- gain coins or progress
- unlock areas
- unlock tools
- trigger story
- return to cubicle / notebook / laptop

### Layer 11. Feedback to issue to update loop

Flow:
1. Player plays.
2. Player submits feedback report.
3. Report is treated as inert text.
4. Agent summarizes problem and creates or updates issue.
5. Agent proposes update.
6. Human approves or rejects update.
7. Only after approval does next gameplay build proceed.

## Serious development milestones

### M0. Governance and delivery stability

Goal: no more nonfunctional button builds.

Deliverables:
- delivery route gate
- human test packet
- no-go registry
- rollback anchor registry

Acceptance:
- GitHub Pages route opens on target device
- navigation works
- review packet available

### M1. RPG onboarding foundation

Goal: recover story-first game start.

Deliverables:
- intro cinematic cards
- application screen
- avatar placeholder
- personal item selection
- Stuff Box / locker close transition

Acceptance:
- player can reach cubicle through the onboarding flow
- no JavaScript-only navigation for essential buttons

### M2. Cubicle core

Goal: create the first stable playable hub.

Deliverables:
- notebook / Somero log
- laptop menu
- desk props
- stand up view
- personal delivery area

Acceptance:
- notebook opens
- laptop opens
- player can stand up and return
- at least one prop is interactable

### M3. RPG systems foundation

Goal: implement dialogue, choices, items, and story flags.

Deliverables:
- dialogue box system
- choice system
- item ownership registry
- achievement dialogue triggers
- supervisor and boss message flow

Acceptance:
- player choice changes story flags
- item state appears in notebook

### M4. Package and logistics foundation

Goal: recover boxes as meaningful packages.

Deliverables:
- box/package types
- labels
- shipping goals
- receive/send areas
- simple delivery progression

Acceptance:
- at least one package can be received, inspected, and sent

### M5. Workspace construction subset

Goal: introduce the 20 x 20 x 20 model as a playable subset.

Deliverables:
- visible grid or room subset
- floor/wall/ceiling build targets
- one or two blocks
- no-clip rule

Acceptance:
- player can place a block
- block placement has gameplay meaning

### M6. Minigames and repair loops

Goal: add farm-like maintenance and repair progression.

Deliverables:
- jam clear minigame
- routing repair
- reward animation
- automatic package alignment after success

Acceptance:
- minigame completion affects main area state

### M7. Portals and time systems reintroduction

Goal: reintroduce ChronoRift identity after stable RPG/logistics base.

Deliverables:
- dedicated portal surfaces
- deterministic portal transform
- item and box state preservation
- time/rift mechanic prototype

Acceptance:
- portal works only on valid surface
- transported item preserves identity

### M8. Public feedback and update cadence

Goal: convert player play into reliable development updates.

Deliverables:
- feedback form
- issue update template
- update proposal template
- human approval gate

Acceptance:
- feedback produces a structured update proposal before new build work

## Required update proposal before next gameplay interaction

Every gameplay iteration must present:

- what was tested
- what failed
- what worked
- what will be changed
- what will not be changed
- which safe point is preserved
- expected human test packet

## Current recommended next build after approval

Build: C6B_RPG_ONBOARDING_FOUNDATION

Scope:
- intro cinematic cards
- application flow
- avatar placeholder
- item selection
- Stuff Box close transition
- cubicle notebook and laptop
- review report

Not included yet:
- physics
- stack boxes
- portal system
- construction grid
- minigame repair loop

## Human approval gate

This development program should be approved before building C6B.

Approval options:
- approve_program
- revise_program
- approve_only_M0_M1_M2
- reject_and_restructure
