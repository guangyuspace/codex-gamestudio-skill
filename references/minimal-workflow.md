# Minimal Game Workflow

Use this reference when a game task needs implementation discipline more than broad design discussion.

## Minimal Studio Pass

Before editing, answer these briefly:

- player-facing outcome: what should the player be able to do or notice
- smallest proof: the smallest code/data/UI slice that proves it works
- existing owners: files, scenes, resources, systems, or tests likely responsible
- verification: the cheapest useful check after the change
- non-goals: what should stay untouched

## Role Selection

Use only the roles needed:

- Producer for scope, phase, risks, and acceptance criteria
- Designer for player intent, rules, content, and tuning
- Engineer for code, data, engine integration, and architecture fit
- UI/UX for HUD, menus, mobile layout, readability, and accessibility
- Artist or Technical Artist for visual direction, import settings, shaders, VFX, or asset pipeline
- QA for repro, smoke tests, regression risk, and release readiness

## Minimal Implementation Rules

- Use existing helpers, engine-native features, and standard library tools before adding dependencies.
- Prefer one focused change over a new framework or abstraction.
- Avoid broad refactors while delivering a feature or fixing a bug.
- Keep edits close to the owning system.
- Add or run focused verification for nontrivial gameplay, save/load, purchase, platform, or UI behavior.
- Do not remove validation, security checks, save safety, purchase guards, accessibility, or error handling just to make the change smaller.

## Phase Flow

1. Inspect current project state and handoff files.
2. Name the phase: design, prototype, development, polish, release, or maintenance.
3. Record assumptions only when they affect scope or risk.
4. Implement the smallest safe slice.
5. Run the relevant check.
6. Update `CODEX_HANDOFF.md` when continuity matters.
7. Report modified files, verification, current risks, and next safest task.

## Stop Conditions

Pause for user confirmation before:

- destructive file operations
- broad architecture rewrites
- core gameplay direction pivots
- publishing, uploads, store submissions, or public release changes
- paid APIs, account settings, billing, platform console configuration, or secret creation
- replacing user-owned art, audio, or project assets when the replacement is subjective
