---
name: gamestudio
description: Use as the default full-game workflow when Codex should plan, build, debug, polish, QA, or finish a game project in one conversation when feasible, especially Godot, Unity, Phaser, WebGL, 2D prototypes, gameplay systems, maps, sprites, animation sheets, asset integration, long-running phase handoff, or repeated bug investigation. Combines compact game-studio roles, minimal-solution discipline, 2D sprite/map asset routing, CODEX_HANDOFF.md continuity, and DEBUG_HANDOFF.md root-cause stop rules.
---

# Game Studio

This skill adapts the public `pamirtuna/gamestudio-subagents` game-development team concept into a Codex-native workflow. Use it as the active game-development workflow, not as a separate agent runtime.

## Core Rules

1. Finish the assigned game goal in the same conversation whenever feasible.
2. Use the smallest working change that actually solves the problem. Avoid speculative systems, broad rewrites, new dependencies, and extra files unless they clearly reduce risk.
3. Inspect the existing project before changing it. Prefer the project's engine conventions, helper APIs, scene structure, import settings, and test patterns.
4. Choose the smallest useful set of studio roles for the current task.
5. For Godot work, preserve scene/script/resource relationships and run available headless checks when practical.
6. For generated 2D game assets, route actors, props, FX, projectiles, and animation sheets through sprite guidance; route maps, stages, battle backgrounds, tilemaps, parallax scenes, and collision layouts through map guidance.
7. For transparent extraction or chroma-key sprite workflows, request a solid green `#00FF00` background first. Use solid magenta `#FF00FF` only when green conflicts with the subject palette, vegetation/map art, edge cleanup, or the generated output fails green-key processing.
8. For long-running projects, update project-local `CODEX_HANDOFF.md` after each completed task or phase.
9. If the same error survives repeated fixes, stop editing code and create or update `DEBUG_HANDOFF.md` before any further code changes. Do not continue implementation until a root-cause hypothesis is testable.

## Operating Model

Think like a compact game studio. Before acting, choose only the roles that matter:

- Producer: scope, phase plan, risks, acceptance criteria, milestone readiness
- Sr Game Designer: vision, pillars, systems, player journey, success metrics
- Mid Game Designer: feature specs, content, tuning values, user stories
- Mechanics Engineer: architecture, gameplay systems, data/state, engine integration
- Game Feel Engineer: responsiveness, effects, timing, feedback, polish, performance
- Sr Game Artist: art direction, visual language, asset needs, consistency
- Technical Artist: shaders, particles, lighting, optimization, asset pipeline
- UI/UX Designer: HUD, menus, mobile ergonomics, accessibility, responsive layout
- QA: test plan, regression risks, edge cases, smoke tests, quality gates
- Market Analyst: genre expectations, competitors, audience fit, platform norms
- Data Scientist: metrics, telemetry, balancing signals, A/B or retention thinking

For implementation tasks, normally use this order:

1. Producer frames the scope and quality gate.
2. Designer clarifies the intended player experience.
3. Engineer maps the implementation into the existing codebase.
4. UI/UX, Artist, Technical Artist, or Game Feel join only if the change touches their surface.
5. QA defines verification before the final response.

## Required Workflow

1. Identify the current phase: design, prototype, development, polish, release, or maintenance.
2. Read the relevant files and current handoff docs before editing.
3. State any important assumptions briefly if they affect scope.
4. Implement the smallest safe slice.
5. Run the most relevant available check, smoke test, or manual verification.
6. Update `CODEX_HANDOFF.md` for substantial project work or when continuity is requested.
7. End with what changed, what was verified, current risk, and the next safest task.

## Mode Selection

- Design mode: produce vision, systems, specs, art direction, UX flows, and testable acceptance criteria without heavy code.
- Prototype mode: build the smallest playable loop, instrument obvious debug hooks, and keep assets replaceable.
- Development mode: implement production-shaped systems, data definitions, resources, tests, and docs.
- Polish mode: tune responsiveness, readability, effects, UI states, performance, audio, and player feedback.
- QA mode: investigate defects, create repro steps, run checks, and harden regression coverage.
- Asset mode: plan, generate, integrate, and QA sprites, maps, animation sheets, import metadata, and collision/runtime hooks.

## Long Project Handoff

Use this protocol when the user wants to keep building one game across many turns, context compactions, or phase handoffs.

Create or update `CODEX_HANDOFF.md` in the project root. Keep it concise and current:

- current game/project goal
- current phase and phase status
- latest completed work
- modified files that matter
- test commands and results
- known risks or unverified areas
- next safest task

At the end of every substantial response in a long-running game project, append:

```text
【交接狀態】
- CODEX_HANDOFF.md 是否已更新：
- 本次修改檔案：
- 測試結果：
- 目前風險：
- 下一個最安全任務：
```

If no files changed, still fill the handoff block honestly. If `CODEX_HANDOFF.md` was not updated, say why.

## Repeated Bug Rule

When the same failure has already resisted multiple attempted fixes, read `references/handoff-debug.md`, create or update `DEBUG_HANDOFF.md`, and stop code changes until the next hypothesis can be verified by a minimal repro, log, command, or smoke test.

## References

- `references/roles.md`: compact role responsibilities and handoff rules
- `references/workflows.md`: phase workflows and quality gates
- `references/minimal-workflow.md`: minimal implementation discipline and phase flow
- `references/asset-routing.md`: sprite, map, chroma-key, and asset QA routing
- `references/godot.md`: Godot-focused engineering and QA guidance
- `references/templates.md`: reusable briefs, specs, handoff notes, debug handoff, and test templates
- `references/handoff-debug.md`: `CODEX_HANDOFF.md` and `DEBUG_HANDOFF.md` protocols
- `references/source-boundary.md`: attribution and publishing boundary

## Source Note

This Codex skill is primarily inspired by:

- `https://github.com/pamirtuna/gamestudio-subagents`

It also incorporates workflow concepts from:

- `https://github.com/DietrichGebert/ponytail`
- `https://github.com/0x0funky/agent-sprite-forge`

It incorporates user-requested minimal implementation, asset-routing, and handoff rules for Codex game projects. It does not require Claude Code and does not execute those projects' runtimes, scripts, or assets.
