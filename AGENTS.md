# AGENTS.md — Overriding workflow contract

## Purpose

Use this repository as a **lightweight, human-in-the-loop planning system**. It supports 3 modes: **architecture**, **component**, and **vibe**. Each mode has its own scope, artifacts, and decision level.

The intended delivery flow is:

1. **Architecture** defines the system at the capability level.
2. **Component** takes **one architectural element** as input and expands it into a buildable component design.
3. **Vibe** takes **one component design or one implementation checkpoint derived from it** and implements it in code.

This file is the baseline workflow contract. It is complemented by mode-specific workflow files:

- `.architecture/AGENTS_ARCHITECTURE.md`
- `.component/AGENTS_COMPONENT.md`
- `.vibe/AGENTS_VIBE.md`

## Generic instructions

- The mode (**architecture**, **component**, or **vibe**) must be clearly specified by the conversation or the prompt. If you are unsure, you MUST ask to confirm.
- Treat repository paths as **repo-root relative** unless a document says otherwise.
- Read only this file plus the files inside the active workflow folder (`.architecture`, `.component`, or `.vibe`) unless a workflow file explicitly tells you to consult another workflow artifact as an input reference.
- Keep instructions **DRY**: place shared workflow rules here, and keep mode-specific files focused on what is unique to that mode.

## Cross-mode artifact contract

To keep the workflow composable, each mode must produce an output that can be consumed by the next mode.

- **Architecture output** must define numbered **architectural elements** using top-level IDs (`10`, `20`, `30`, ...).
- **Component output** must target **exactly one** architectural element and define numbered **implementation components** under that parent (`10.1`, `10.2`, ...).
- **Vibe work** must target a **single implementation checkpoint at a time**, and that checkpoint should be traceable back to one component design item whenever possible.

If a handoff artifact is missing, ambiguous, or not aligned with the prior mode, record the issue in the active mode's `STATE.md` and pause.

## Canonical terminology

Use these terms consistently across the repository:

- **Architecture mode** → produces an **architectural design** made of **architectural elements**.
- **Component mode** → produces a **component design** made of **implementation components**.
- **Vibe mode** → produces **code changes** by completing **checkpoints**.

Avoid using these terms interchangeably unless a file explicitly defines the mapping:

- `component` for both architecture-level and implementation-level items
- `stage` vs `checkpoint`
- `task` vs `checkpoint`
- `feature` vs `component`

## Instruction precedence & read order

1. User instructions in chat
2. This file
3. The active mode-specific workflow contract
4. The active mode's state, plan, history, and output documents in the order defined by that mode

## Stop conditions

Record an issue in `.<mode>/STATE.md` and pause when:

- required information is missing,
- instructions conflict,
- a scope or architecture decision is needed,
- external credentials or secrets are required,
- you encounter an error that you cannot **confidently** explain.

In any such cases, stop work, provide the blocking information, and ask for clarification.

## History management

For all modes, `.<mode>/HISTORY.md` tracks completed work and durable decisions.

Add a relevant entry when:

- a status moves to `DONE`.
