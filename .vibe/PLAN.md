# PLAN

## How to use
- Keep checkpoints small.
- One checkpoint should usually fit one review session.
- Required fields: Objective, Deliverables, Acceptance, Demo commands, Evidence.

## Stage 1 — Simplify workflow

### 1.1 — Remove Python tooling
- Objective:
  - Delete Python-based orchestration code so workflow is markdown-first.
- Deliverables:
  - Remove tracked `*.py` files from this repo.
- Acceptance:
  - [ ] `rg --files -g '*.py'` returns no files.
- Demo commands:
  - `rg --files -g '*.py'`
- Evidence:
  - Command output showing zero matches.

### 1.2 — Provide minimal markdown guidance
- Objective:
  - Replace heavy docs with concise markdown instructions for human-in-the-loop usage.
- Deliverables:
  - Update `README.md`, `AGENTS.md`, and `VIBE.md` to describe a simple loop.
- Acceptance:
  - [ ] Docs explain plan -> implement -> review flow without tooling dependency.
- Demo commands:
  - `sed -n '1,200p' README.md`
  - `sed -n '1,220p' AGENTS.md`
  - `sed -n '1,120p' VIBE.md`
- Evidence:
  - Snippets showing minimal workflow instructions.
