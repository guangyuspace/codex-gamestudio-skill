# Handoff And Debug Protocols

Use this reference for long-running game work, context compaction, overnight work, or repeated unresolved defects.

## CODEX_HANDOFF.md

Create or update `CODEX_HANDOFF.md` in the project root when the work needs continuity across turns, phases, or chats.

Keep it current and short:

```md
# CODEX_HANDOFF

## Project Goal

## Current Phase
- Phase:
- Status:

## Latest Completed Work
-

## Important Modified Files
-

## Verification
- Command:
- Result:

## Known Risks
-

## Next Safest Task
-
```

End substantial responses with:

```text
【交接狀態】
- CODEX_HANDOFF.md 是否已更新：
- 本次修改檔案：
- 測試結果：
- 目前風險：
- 下一個最安全任務：
```

## DEBUG_HANDOFF.md

If the same error has survived repeated fixes, create or update `DEBUG_HANDOFF.md` before further code edits.

Use this structure:

```md
# DEBUG_HANDOFF

## 錯誤現象

## 最小重現步驟

## 目前錯誤訊息 / log

## 已嘗試修法

## 失敗原因

## 根因假設

## 下一個驗證步驟

## 不准再重複的修法
```

## Debug Stop Rule

- Before editing, state the current root-cause hypothesis.
- Before fixing, define the smallest test, command, log, scene, or repro that can disprove the hypothesis.
- After editing, run that check.
- If the hypothesis fails twice, stop and update `DEBUG_HANDOFF.md` instead of trying another similar fix.
- Do not repeat fixes listed under `不准再重複的修法`.
- Do not start a broad refactor while the root cause is unproven.

## Overnight Or Long Runs

When the user asks Codex to continue while they are away:

- keep changes incremental
- run checks after each meaningful slice
- update `CODEX_HANDOFF.md` after each completed slice
- update `DEBUG_HANDOFF.md` when a repeated blocker appears
- leave the repo in a reviewable state
