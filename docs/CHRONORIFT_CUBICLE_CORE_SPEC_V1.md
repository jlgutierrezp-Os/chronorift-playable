# CHRONORIFT_CUBICLE_CORE_SPEC_V1

Status: design specification. No runtime replacement.

## Purpose

Define the cubicle as the first stable playable hub. The cubicle is not a menu overlay; it is an in-world RPG room where the player learns work, identity, progress, requests, and small automation tricks.

## Cubicle core elements

### Notebook / save log

The notebook is the visible progress and recovery object.

Must show:

- story progress
- current stage
- obtained items
- current item ownership
- skills
- achievements
- unlocked abilities
- Somero summary

### Laptop / work computer

The laptop is the work-and-story hub.

Functions:

- supervisor messages
- boss messages
- stage goals
- achievements
- 3D printer block requests
- mini-game selection
- personal delivery requests

### Desk props

Core props:

- bird pendulum toy
- adhesive tape
- small office items

Bird pendulum functions:

- can be inspected
- can be picked up
- can be activated
- can later press buttons semi-automatically

Tape functions:

- can hold buttons pressed
- can combine with sticks in story scenes

### Stand up / room transition

The player can exit seated desk view and enter cubicle room view.

Room view should include:

- visible desk
- notebook
- laptop
- locker or Stuff Box reference
- personal delivery area
- exit to future areas

### Personal delivery area

The cubicle has a small receive/send zone for personal packages.

Functions:

- request packages through laptop
- receive special labeled boxes
- interact with package contents

## Future cubicle unlocks

- meditation area
- yoga area
- exercise area
- reading area
- music area

These areas represent life beyond work and should unlock visually and narratively.

## Interaction model

Every important object must support context actions:

- inspect
- use
- take
- combine where appropriate
- log discovery

## First-pass acceptance

- Player can understand the cubicle layout.
- Notebook opens and shows progress.
- Laptop opens and shows functional categories.
- Stuff Box/locker continuity is visible.
- Player can stand up and return to desk.
- At least one desk object has a meaningful interaction.

## Not in scope

- Heavy inventory database.
- Multiplayer cubicle interaction.
- Public write access.
- Core runtime replacement without human approval.
