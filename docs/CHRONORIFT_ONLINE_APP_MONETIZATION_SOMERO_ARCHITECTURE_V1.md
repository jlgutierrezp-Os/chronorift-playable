# CHRONORIFT_ONLINE_APP_MONETIZATION_SOMERO_ARCHITECTURE_V1

Status: future online/app monetization architecture. No runtime replacement. No payment implementation. No credential storage.

## Purpose

Clarify that ChronoRift is currently being developed as a web game, but is intended to function online and may later be monetized if viable through an App-connected layer. The web game and the App should share the same core game base, but the App can contain player identity, recoverable state, memories, personalizations, and optional market features.

## Current phase

```yaml
CURRENT_PHASE:
  active_development: web_game
  active_runtime: GitHub_Pages_or_equivalent_static_web
  app_development: future_connected_layer
  payment_development: not_active
  server_infrastructure_goal: minimal
  core_game_base: shared
```

The current project remains web-first. The App is a future connection layer, not a replacement for the current web build.

## Product split

### Web version

Purpose:
- public play
- frictionless testing
- basic game access
- no required login
- no personalized persistent account requirement
- no app-only inventory features

Web users can:
- play public builds
- submit feedback as inert text
- test game loops
- experience base story and public stages

Web users should not:
- access app-only memories
- access personalized item storage
- access private player inventory
- access app marketplace ownership
- mutate repo/runtime

### App version

Purpose:
- player registration if monetization is viable
- persistent player identity
- player-owned memories/state
- custom items
- custom images
- app-only options visible in common areas
- optional free/paid marketplace or customization layer
- low-infrastructure Somero recovery

App users can eventually:
- create player profile
- save local or synced state
- recover using Somero phrases
- personalize items and images
- display app-only customizations in common areas
- access additional cosmetic or RPG options

## Monetization principle

Monetization should be viable only if it adds user value without making the base web game feel broken or predatory.

Potential monetization should focus on:
- personalization
- optional cosmetics
- custom item skins
- custom image slots
- expanded avatar options
- expanded Stuff Box themes
- extra non-pay-to-win narrative branches
- creative marketplace items
- convenience recovery or cloud sync if needed

Avoid:
- pay-to-win progression
- gambling mechanics
- predatory scarcity
- required payment for core story completion
- paid access to basic accessibility or recovery functions

## Somero architecture

Somero should remain ephemeral, recoverable, and low infrastructure.

Core idea:
- state is recoverable through short human-readable name-word ledgers
- local state can exist on device
- app account can improve convenience, not become mandatory for the base web game
- no heavy server infrastructure should be required for the basic loop

```yaml
SOMERO_STATE_MODEL:
  layers:
    web_local:
      storage: browser_local_storage_or_equivalent
      account_required: false
      recoverable_by_phrase: true

    app_local:
      storage: app_local_storage
      account_required: optional
      recoverable_by_phrase: true

    app_sync_optional:
      storage: minimal_backend_or_platform_sync_later
      account_required: true
      active_now: false
      purpose:
        - convenience
        - cross_device_restore
        - app_market_ownership_if_added
```

## Name-word ledger

The name-word ledger works as a compact state carrier.

Examples:
- SAIREN-STUFFBOX-CUBICLE-STABLE-FIRSTLOG
- LOOP-CH1-GIZMO-HINT-ENERGY-STABLE
- CHIP-LOST-PRWORM-RISE-RECOVERY-SEED

Fields:
- player alias
- chapter
- stage
- energy state
- gizmo state
- item state
- achievements
- badges
- story flags
- public/private visibility marker

Constraints:
- short enough to copy
- human readable
- no secrets
- no passwords
- no private clinical or real-world sensitive data
- not an authentication system

## App-only personalization

App-only features may include:
- avatar visual variants
- personal item skins
- custom Stuff Box labels
- image slots for in-game decorations
- personal office/cubicle decoration
- small gizmo skins
- badge display shelves
- personal memory cards
- non-public item notes
- optional market-purchased or earned items

Visibility rule:
- app user can see their personal/custom items in common areas
- web-only user sees base/default public assets
- app-only personalized assets should degrade gracefully to defaults on web

## Common area visibility

The common area can show app-player identity and customizations only if safe and appropriate.

Common area examples:
- cubicle decoration
- Stuff Box visual label
- avatar accessory
- display badge
- custom package sticker
- small office plant/bonsai
- gizmo skin

Privacy rule:
- never expose private account data in public common areas
- custom images must be moderated or locally private until safety process exists
- public display should be opt-in

## Marketplace options

The best early monetization direction is not mandatory purchase. It is optional customization.

Potential market categories:
- cosmetic item packs
- office/cubicle themes
- gizmo skins
- badge frames
- personal item art
- avatar accessories
- optional story flavor packs
- community-created decorations if governance exists

Market should not be added until:
- base onboarding works
- inventory/storage works
- Somero recovery works
- personalization schema exists
- privacy and moderation rules exist

## Low infrastructure strategy

Preferred path:
1. Web game static build.
2. Local browser persistence.
3. Somero name-word ledger recovery.
4. App wrapper or native app later.
5. Optional app account.
6. Optional sync/market backend only if validated by user demand.

Do not start with heavy servers, complex accounts, or expensive infrastructure.

## Data categories

### Safe local game state

- chapter
- stage
- achievements
- badges
- item state
- energy state
- gizmo state
- selected avatar
- unlocked cosmetics
- Somero code

### App account state, future only

- profile id
- app entitlements
- market purchases if enabled
- custom visuals metadata
- cloud sync state

### Avoid storing by default

- sensitive personal data
- private real-world notes
- external credentials
- payment credentials in game code
- public unmoderated images

## Development phases

### Phase W0. Current web foundation

Build static and lightweight playable web foundation.

### Phase W1. Local save and Somero phrase

Add local state and phrase recovery without accounts.

### Phase W2. Personalization schema

Define item skins, avatar variants, Stuff Box labels, and badge displays.

### Phase A0. App shell candidate

Future: package the same core game inside an app wrapper or native shell.

### Phase A1. Optional account layer

Future: allow account registration only when needed for sync, market, or persistent app identity.

### Phase A2. Optional market

Future: add cosmetics/market only after product viability and privacy/moderation rules.

## Approval gate before monetization implementation

No monetization implementation should start until:
- core onboarding is playable
- local save works
- Somero phrase works
- inventory/state schema works
- privacy boundary is defined
- store or market plan is reviewed
- human approval is explicit

## Current implication

C6B should not implement monetization or accounts.

C6B may include future-facing placeholders:
- Somero code field
- locked App-only personalization placeholder
- default Stuff Box customization slot
- explanation that App features are future and not required for web play

## Next recommended artifact

After C6B screen script pack, create:

CHRONORIFT_SOMERO_LEDGER_SCHEMA_V1

It should define:
- encoded fields
- phrase examples
- local storage shape
- app-future extension fields
- privacy constraints
- web/app feature separation
