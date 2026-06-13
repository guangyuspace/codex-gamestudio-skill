# Godot Guidance

Use this reference for Godot 4 projects.

## Project Reading Order

1. `project.godot`
2. relevant scenes under `scenes/`
3. scripts attached to those scenes
4. autoloads and services
5. resources under `resources/`
6. tests or smoke scripts

## Engineering Rules

- Preserve existing node names and exported properties unless the task requires a change.
- Prefer signals, resources, and small services when the project already uses them.
- Keep scene wiring and script logic aligned. If a script expects a node, verify the scene has it.
- Avoid mixing debug-only UI with gameplay state unless there is an existing debug panel pattern.
- Put tunable gameplay numbers in resources or constants that match local conventions.
- Be careful with save data shape, autoload initialization order, and scene reloads.

## Common Godot Deliverables

- `.gd` scripts for runtime behavior
- `.tscn` scene edits for nodes and UI
- `.tres` resources for content, characters, enemies, chips, pieces, skills, towers, waves, items, or tuning
- smoke tests under the project's existing test location
- design docs under `docs/`

## Game Feel Checklist

- Input responds immediately or visibly queues.
- Damage/heal/status changes have feedback.
- Important state changes are readable without watching logs.
- Animations and tweens do not block core simulation.
- Effects have sane durations and do not obscure the board/HUD.

## UI/UX Checklist

- Text fits on desktop and mobile viewports.
- Touch targets are large enough for mobile.
- Critical state is not color-only.
- Empty, disabled, selected, and error states are handled.
- HUD does not cover primary gameplay.

## QA Checks

Prefer the project's existing Godot executable and check scripts. Useful checks include:

- GDScript syntax check for changed scripts
- headless scene load
- smoke test for the feature phase
- manual checklist for player path, reset/retry, and viewport size

When tools are unavailable, state exactly what was not run.
