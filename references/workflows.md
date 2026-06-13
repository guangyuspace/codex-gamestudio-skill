# Game Studio Workflows

## Design Mode

Use when the user wants ideas, specs, phase planning, systems, UX, balance, content, or art direction.

Workflow:

1. Define target player experience and core loop.
2. State 3-5 design pillars.
3. Identify platform and engine constraints.
4. Produce feature specs with acceptance criteria.
5. Add QA checks before implementation begins.

Deliverables:

- game vision brief
- feature specification
- content/balance table
- UX flow
- art direction brief
- QA checklist

## Prototype Mode

Use when the user wants a playable proof quickly.

Workflow:

1. Identify the one loop that must be playable.
2. Keep assets replaceable and systems small.
3. Build minimum input, feedback, win/loss or completion state, and debug visibility.
4. Verify the loop in engine or browser when possible.
5. Document what was intentionally left rough.

Quality gate:

- The user can play the core interaction without hidden setup.
- Failure states are visible.
- Debug logs or UI reveal enough state to diagnose issues.

## Development Mode

Use when implementing production-shaped features.

Workflow:

1. Read relevant files before editing.
2. Follow existing naming, scene, resource, service, and test patterns.
3. Keep data definitions separate from runtime behavior when the project already does so.
4. Preserve save/load and progression compatibility where relevant.
5. Add focused verification.

Quality gate:

- Feature works through the intended player path.
- Shared systems have regression coverage or a manual checklist.
- No unrelated refactors.

## Polish Mode

Use when improving feel, readability, UI, audio, VFX, animation, or performance.

Workflow:

1. Identify the action or state that lacks feedback.
2. Tune timing, scale, color, motion, sound, or camera feedback.
3. Check readability at target viewport sizes.
4. Keep effects optional or tunable.
5. Verify performance and avoid clutter.

Quality gate:

- Player can understand what happened and why.
- Feedback reinforces the action without hiding gameplay state.

## QA Mode

Use when debugging, reviewing, or preparing release.

Workflow:

1. Reproduce or infer the failure path.
2. Identify impacted systems and regression risks.
3. Check edge cases, state transitions, and restart/reload behavior.
4. Run available automated checks.
5. Report remaining risk clearly.

Quality gate:

- Clear repro or clear statement that repro was not possible.
- Fix is verified by command, smoke test, or manual checklist.
- Any untested surface is named.
