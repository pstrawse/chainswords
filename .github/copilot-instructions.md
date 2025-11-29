<!-- Purpose: concise guidance for AI coding agents working on this repo -->
# Copilot instructions — chainswords

Purpose: provide precise, repo-specific guidance for AI coding agents so they can be immediately productive.

Repository snapshot
- Single-file static site: the only source file is `index.html` at the repository root (currently empty).
- There is no `package.json`, no build system, no tests, and no CI configuration in the repository.

What this repository expects from an AI agent
- Minimal, conservative edits: change only files required to implement a requested feature or bugfix.
- Do not introduce large new toolchains (Webpack, React, etc.) without an explicit issue or human approval.
- When adding new files or folders, update the README and include run/preview instructions.

Local preview and developer workflows
- Quick local preview (no install):
  - `python -m http.server 8000` and open `http://localhost:8000`
  - or: `npx serve .` if Node is available
- If you propose adding dev tooling (linters, bundlers, formatters), include a small `package.json` and a short justification in the PR description.

Project-specific patterns and conventions
- Filenames: use lowercase and hyphen-separated names (e.g., `styles/main.css`, `scripts/app.js`).
- Keep the root lightweight: prefer `assets/` or `static/` directories for images, CSS, and JS rather than cluttering the repo root.
- HTML edits should be semantic and minimal — change structure only when necessary.

Examples (how to perform common tasks)
- Add a CSS file and wire it into the page:
  1. Create `styles/main.css`.
  2. Add `<link rel="stylesheet" href="styles/main.css">` inside the `<head>` of `index.html`.
- Add a small JS module:
  1. Create `scripts/app.js` and add `<script src="scripts/app.js" defer></script>` before `</body>`.

Integration and external dependencies
- There are currently no external services or integration points tracked in the repo.
- If you add third-party dependencies (CDNs or npm packages), document them in the PR and in a new `README.md`.

Commit / PR guidance for agents
- Keep commits small and focused. Each PR should include:
  - Short summary of intent and files changed.
  - Local preview instructions and a short testing checklist (manual steps if no tests exist).
  - Rationale for new tooling or large structural changes.
- Avoid committing generated files or dependency directories (e.g., `node_modules/`).

When unsure
- Ask a human: if a change requires adding a build system, changing project scope, or touching many files, open an issue or ask for confirmation before proceeding.

Contact and iteration
- After making changes, request feedback in the PR and include any open questions as checklist items.

Notes for maintainers
- This file was generated from the repository state: single `index.html` and no build/test tooling. Update this guidance if you add CI, tests, or other infrastructure.
