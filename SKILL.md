---
name: gamestudio
description: Use when building, planning, balancing, testing, or polishing a game project, especially Godot, Unity, Phaser, or 2D prototype work that benefits from a multi-discipline game studio workflow with producer, designer, engineer, artist, UI/UX, analytics, and QA perspectives.
metadata:
  short-description: Multi-role game studio workflow for Codex
---

# Game Studio

This skill adapts the public `pamirtuna/gamestudio-subagents` game-development team concept into a Codex-native workflow. Use it as a disciplined studio lens, not as a separate agent runtime.

## When To Use

Use this skill when the user asks to:

- plan or build a game feature, phase, prototype, demo, vertical slice, or full game
- work on Godot, Unity, Phaser, WebGL, or general 2D/3D gameplay code
- design battle systems, boards, progression, economy, UI/HUD, content, levels, maps, or game feel
- review a game feature for quality, polish, performance, UX, or release readiness
- coordinate multiple game-development concerns before implementation

Do not use this skill for isolated non-game code tasks unless game domain judgment matters.

## Operating Model

Think like a compact game studio. Before acting, choose the smallest useful set of roles:

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

1. Inspect existing project structure first. Prefer local architecture and engine conventions.
2. Identify the current phase: design, prototype, development, polish, release, or maintenance.
3. State any important assumptions briefly if they affect scope.
4. Create or update only the files needed for the requested game change.
5. For Godot work, preserve scene/script/resource relationships and run available headless checks when practical.
6. End with what changed, what was verified, and the next useful studio task.

## Mode Selection

- Design mode: produce vision, systems, specs, art direction, UX flows, and testable acceptance criteria without heavy code.
- Prototype mode: build the smallest playable loop, instrument obvious debug hooks, and keep assets replaceable.
- Development mode: implement production-shaped systems, data definitions, resources, tests, and docs.
- Polish mode: tune responsiveness, readability, effects, UI states, performance, and player feedback.
- QA mode: investigate defects, create repro steps, run checks, and harden regression coverage.

## Deliverables

Choose deliverables that fit the request:

- feature brief
- implementation plan
- Godot scene/script/resource changes
- gameplay system code
- tuning table or resource data
- UX flow or HUD layout
- art direction or asset request list
- smoke test or QA checklist
- bug report with repro and acceptance criteria
- phase completion report

## References

- `references/roles.md`: compact role responsibilities and handoff rules
- `references/workflows.md`: phase workflows and quality gates
- `references/godot.md`: Godot-focused engineering and QA guidance
- `references/templates.md`: reusable briefs, specs, and test templates

## Source Note

This Codex skill is a concise adaptation inspired by:

`https://github.com/pamirtuna/gamestudio-subagents`

It does not require Claude Code and does not execute that repository's sub-agent runtime. Use the linked project as source inspiration and this skill as the active Codex workflow.
