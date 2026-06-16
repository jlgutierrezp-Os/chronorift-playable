# Security Policy

This repo is intentionally isolated as a public, disposable game-runtime layer.

## Forbidden in this repository

- Secrets, tokens, credentials, `.env` files.
- Package managers or dependency installs.
- External scripts/CDNs unless explicitly approved later.
- GitHub Actions unless explicitly approved after a security gate.
- PR/issue/comment-triggered automation.
- Cross-repository writes or access to ancestor repositories.

## Allowed now

- Static files: `index.html`, `style.css`, `app.js`.
- Documentation: `README.md`, `SECURITY.md`, `CHANGELOG.md`.
- Manual human-approved updates through the connected GitHub tool.

## Reporting

Use the in-game SelfDebug panel and paste the generated report into the controlling ChatGPT/LUU thread.
