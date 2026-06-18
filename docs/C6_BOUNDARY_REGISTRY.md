# C6 Boundary Registry

Status: active review constraint for ChronoRift C6 planning.

## Allowed

- Standalone candidate builds for human review.
- Review documents, test matrices, and GitHub issues.
- Browser-style automated tests when available.
- Local set-content tests for survey and launcher behavior.
- Preserve confirmed C4 and C5 achievements.
- Design structural changes as candidates before runtime update.
- Use no-cost tools and local-first code.
- Use GitHub Pages delivery gate before human handoff.

## Not in scope

- Do not replace app.js without explicit human review and approval.
- Do not claim playable confirmation without human test.
- Do not claim remote browser play if navigation is blocked.
- Do not auto-send ChatGPT messages from GitHub Pages.
- Do not add paid APIs, credentials, camera login, QR scan, or external accounts.
- Do not use copied branded game content.
- Do not ship placeholder-only builds as playable.
- Do not repeat a failed delivery route without a preventive fix.
- Do not deliver sandbox/local external-file builds as runnable on iPhone.
- Do not hand off any build whose buttons have not passed functional review.

## Current environment result

- GitHub Pages remote navigation in the agent browser was blocked.
- Local HTML survey was testable with set-content browser execution.
- Sandbox/local external-file candidate failed in human test because visible buttons did not function.
- GitHub HTML direct create attempts were blocked during this interaction.
- Updating an existing GitHub Pages HTML gate succeeded.
- Markdown review files were created successfully.

## Human gate

A C6 structural build may be created as a standalone candidate for review, but it must not replace the core runtime until human approval.

## Delivery gate

Before the next C6 link is handed off, a GitHub Pages route must be confirmed as openable and responsive on the user's device. The temporary delivery gate is tests/chronorift_C5_play_survey_submit.html.
