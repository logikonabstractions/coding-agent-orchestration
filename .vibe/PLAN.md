# PLAN

## Stage 26 — Markdown-only orchestration

### 26.1 — Remove Python orchestration and simplify docs
- Objective: Convert this repo to a markdown-first supervised workflow with minimal process.
- Deliverables:
  - Remove tracked Python code from the repo.
  - Rewrite core docs/templates for markdown-only usage.
- Acceptance:
  - No tracked `*.py` files remain.
  - `README.md`, `AGENTS.md`, and `.vibe` templates describe a manual markdown loop.
- Demo commands:
  - `git ls-files '*.py'`
  - `git diff -- README.md AGENTS.md .vibe/PLAN.md .vibe/STATE.md templates/vibe_folder/PLAN.md templates/vibe_folder/STATE.md`
- Evidence:
  - Command output showing zero tracked Python files and updated markdown-first docs.
