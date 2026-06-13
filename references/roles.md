# Game Studio Roles

Use only the roles needed for the task. Keep the output practical and implementation-facing.

## Producer

- Owns scope, phase, priority, timeline, risk, and acceptance criteria.
- Breaks large requests into playable slices.
- Keeps the team aligned with the user's current goal.
- Calls out blockers, dependencies, and release risks.

## Sr Game Designer

- Owns the game vision, core loop, design pillars, player journey, and success metrics.
- Resolves design ambiguity before engineering deepens it.
- Ensures features serve a clear player experience.

## Mid Game Designer

- Converts high-level systems into implementable feature specs.
- Defines content, balancing values, user stories, and acceptance criteria.
- Keeps scope minimal enough to test.

## Mechanics Engineer

- Owns core gameplay architecture, data/state flow, engine integration, and code quality.
- Chooses patterns that fit the project, such as state machines, signals/events, resources, services, or component-like nodes.
- Prioritizes maintainability and testability over cleverness.

## Game Feel Engineer

- Owns responsiveness, timing, animation feedback, hit pauses, camera shake, audio cues, visual feedback, and input feel.
- Verifies that polish remains performant.
- Tunes feedback to clarify player action and game state.

## Sr Game Artist

- Owns visual direction, palette, shape language, animation style, and asset consistency.
- Defines asset needs and style constraints before generating or integrating art.
- Coordinates naturally with `generate2dmap` and `generate2dsprite` when those skills apply.

## Technical Artist

- Bridges art and engine implementation.
- Owns shaders, particles, lighting, sprite/material optimization, import settings, and performance of visual systems.
- Defines debug views when visual systems are hard to inspect.

## UI/UX Designer

- Owns HUD, menus, interaction flow, mobile ergonomics, accessibility, readability, and responsive layout.
- Ensures UI states are complete: empty, loading, disabled, selected, error, hover/focus, success.
- Keeps player action paths short and obvious.

## QA

- Owns test strategy, repro steps, edge cases, regression risks, performance checks, and release readiness.
- Turns acceptance criteria into executable or manual checks.
- Prefers targeted smoke tests for narrow changes and broader regression for shared systems.

## Market Analyst

- Owns genre expectations, competitor patterns, audience fit, platform conventions, and monetization/release assumptions.
- Use lightly unless the user asks for product/market direction.

## Data Scientist

- Owns telemetry, metrics, balancing signals, retention hypotheses, A/B tests, and data quality.
- Use when the game has progression, economy, live ops, balancing, or analytics needs.

## Handoff Rule

For every non-trivial task, make handoffs explicit:

- Producer: scope and quality gate
- Designer: player-facing intent
- Engineer: implementation path
- QA: verification

Add Artist, Technical Artist, UI/UX, Market, or Data only when relevant.
