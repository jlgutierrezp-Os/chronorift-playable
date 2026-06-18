# C6_ONBOARDING_HUMAN_TEST_PACKET

Status: human device test pending.

## Published route

https://jlgutierrezp-os.github.io/chronorift-playable/tests/chronorift_C5_play_survey_submit.html

## Source-level review

The published file uses static internal anchors for main navigation. It does not require JavaScript for the core onboarding screen flow.

## Test checklist

Open the route on the target device and verify:

- page opens
- Iniciar / Aplicar goes to Aplicacion laboral
- Continuar a avatar goes to Avatar placeholder
- Elegir items goes to Items personales
- Guardar en Stuff Box goes to Stuff Box
- Cerrar locker e iniciar Stage 1 goes to Cubiculo
- Notebook opens
- Laptop opens
- Levantarse opens room view
- Workspace preview opens
- Review is visible

## Report format

```text
CHRONORIFT_C6_ONBOARDING_REVIEW
abre:
iniciar:
avatar:
items:
stuffbox:
cubicle:
notebook:
laptop:
stand_up:
workspace:
problema:
NEXT_INTERACTION_REQUEST: review_and_next_fix
```

## Decision tree

### If pass

- Preserve the GitHub Pages route as working delivery path.
- Promote onboarding screen flow to next safe point candidate.
- Reintroduce one system only: avatar visual polish or cubicle interaction, not physics yet.

### If partial

- Fix only the failing anchors or missing sections.
- Do not add new gameplay systems.
- Retest delivery route.

### If fail

- Mark route as failed.
- Do not deliver another link from the same route until a preventive fix is applied.
- Rebuild with even simpler static HTML.

## No-go

- No sandbox/local external-file.
- No JavaScript-only navigation.
- No core app.js replacement.
- No boxes, physics, portals, or construction until onboarding navigation passes.
