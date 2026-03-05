# Vibe Coding-Agent Orchestration (version Basic: Markdown-only)

This repository tracks agentic work using files states only

## Core files

- `AGENTS.md` — execution contract
- `.vibe/PLAN.md` — checkpoints and acceptance criteria
- `.vibe/STATE.md` — current active checkpoint and status
- `.vibe/HISTORY.md` — optional archive/summaries
- `.vibe/CONTEXT.md` — optional context handoff notes

## Workflow loop

1. Read `AGENTS.md`, `.vibe/STATE.md`, `.vibe/PLAN.md`.
2. Pick the active checkpoint from `.vibe/STATE.md`.
3. Implement only that checkpoint.
4. Run any required demo/test commands.
5. Update `.vibe/STATE.md` with work log + evidence.
6. Open a PR
7. Human reviews.

## Checkpoint template (PLAN.md)

```md
### <stage>.<n> — <title>
- Objective:
- Deliverables:
- Acceptance:
- Demo commands:
- Evidence:
```

## State template (STATE.md)

```md
## Current focus
- Stage: <id>
- Checkpoint: <id>
- Status: NOT_STARTED|IN_PROGRESS|IN_REVIEW|BLOCKED|DONE

## Work log (current session)
- YYYY-MM-DD: <change summary>

## Evidence
- `<command>` -> <result>

## Active issues
- [ ] ISSUE-<id>: <title>
  - Impact: QUESTION|MINOR|MAJOR|BLOCKER
  - Status: OPEN|IN_PROGRESS|BLOCKED|RESOLVED
  - Owner: agent|human
  - Unblock Condition: <condition>
  - Evidence Needed: <proof>
```

## Philosophy

Keep it simple:
- small checkpoints,
- frequent human review,
- no autonomous long-running loops.
