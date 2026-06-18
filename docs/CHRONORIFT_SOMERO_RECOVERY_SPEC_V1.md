# CHRONORIFT_SOMERO_RECOVERY_SPEC_V1

Status: design specification. No runtime replacement.

## Purpose

Define a lightweight recovery system for ChronoRift progress without requiring a traditional database or public account system.

## Core principle

The player name functions as a recovery anchor or save point. It can encode or bind to a compact progress summary called Somero.

## Somero payload

A Somero recovery payload should represent:

- player name
- selected avatar
- avatar features
- personal items selected
- current item ownership
- story progress
- current stage
- skills unlocked
- achievements
- important flags
- PR Worm related state

## Recovery goals

- Restore a lightweight version of progress.
- Avoid database dependency in early builds.
- Preserve story continuity.
- Preserve personal item consequences.
- Preserve who has each item.
- Let the notebook display recoverable progress.

## Example state fields

```yaml
somero_payload:
  player:
    name: string
    avatar_id: string
    traits: []

  items:
    phone:
      owner: player_or_stuffbox_or_supervisor_or_unknown
      known: true
    phone_chip:
      owner: player_or_stuffbox_or_supervisor_or_missing
      known: true
    tape:
      owner: player_or_stuffbox_or_desk
    sticks:
      owner: player_or_stuffbox_or_scene

  progress:
    stage: string
    story_flags: []
    skills: []
    achievements: []

  world:
    current_area: cubicle_or_workspace_or_other
    unlocked_areas: []
```

## Save source

Primary source:

- notebook / journal summary

Secondary source:

- laptop achievement and stage menu
- Stuff Box item registry
- issue/test reports during development

## Cheat-code risk

The system may create cheat-code-like recovery side effects later. This is acceptable if documented, but it should not allow public users to mutate the repository, backend, or other players.

## Security boundary

Somero is an in-game recovery model, not an authorization system.

It must not:

- grant repository access
- grant admin access
- write to GitHub
- use secrets
- execute code
- change public game files

## Acceptance

- Player can see a simple recoverable summary.
- Notebook can show what would be recovered.
- Personal item ownership is trackable.
- PR Worm can alter item ownership.
- Recovery remains local/static-friendly in early versions.
