# STATE

## Current focus
- Stage: 26
- Checkpoint: 26.1
- Status: IN_REVIEW  <!-- NOT_STARTED | IN_PROGRESS | IN_REVIEW | BLOCKED | DONE -->

## Objective (current checkpoint)
- Convert this repo to a markdown-first supervised workflow with minimal process.

## Deliverables (current checkpoint)
- Remove tracked Python code from the repo.
- Rewrite core docs/templates for markdown-only usage.

## Acceptance (current checkpoint)
- No tracked `*.py` files remain.
- `README.md`, `AGENTS.md`, and `.vibe` templates describe a manual markdown loop.

## Work log
- 2026-03-05: Removed all tracked Python files (`tools/`, tests, `.codex` scripts, and helpers) and replaced core workflow docs/templates with markdown-only guidance.
- 2026-03-05: Validation checks run: `git ls-files '*.py'` (no output), plus targeted `git diff` review for rewritten docs/templates.

## Active issues
- None.
