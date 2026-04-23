# Flash – Claude Instructions

## Workflow

- After completing every task, merge all changes to `main` and push.
- The working branch is `claude/fix-flashcard-flip-advance-2DDCQ` (or a new feature branch per task). Always end by merging to `main`.

## Requirements

- After every change, review `REQUIREMENTS.md` to check whether the change adds, modifies, or removes behaviour that should be reflected there. If so, update `REQUIREMENTS.md` as part of the same commit.

## Versioning

- The app displays a version number at the bottom of the UI (`index.html`), in the format `vMAJOR.MINOR.PATCH`.
- Bump the version on every change:
  - **PATCH** (e.g. `1.0.0 → 1.0.1`): bug fixes, visual tweaks, copy changes.
  - **MINOR** (e.g. `1.0.0 → 1.1.0`): new features or behaviour changes that are backwards-compatible.
  - **MAJOR** (e.g. `1.0.0 → 2.0.0`): breaking changes or full redesigns.
- The version string lives in the `<div>` just above the `<script src="cards.js">` tag.
