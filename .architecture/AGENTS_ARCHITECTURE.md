# ARCHITECTURE Workflow Contract

## Purpose

Translate a product or problem statement into an **architectural design**. This further specifies `AGENTS.md` for this mode.

## Instruction precedence & read order
1. As specified by `AGENTS.md`
2. This file
3. `.architecture/ARCHITECTURE_DESCRIPTION.md`
4. `.architecture/STATE.md`
5. `.architecture/PLAN.md`
6. `.architecture/HISTORY.md`

## Meta-templates

| File | Role |
|------|------|
| `ARCHITECTURE_DESCRIPTION.md` | Output template and deliverable for the architectural design |
| `STATE.md` | Current draft, focus, active blockers, work log |
| `PLAN.md` | Blocking architectural questions requiring discussion or decision |
| `HISTORY.md` | Resolved questions, completed review rounds, durable decisions |

## Scope

This mode must define the major architectural elements of the target system, the responsibility of each, how they interact, and the main system-wide concerns.

It must not define implementation strategies or concrete technology choices (for example: specific frameworks, databases, cloud products, or vendors).

## Core output

The deliverable is a markdown document that gives a **structured architectural breakdown** of the proposed solution, conforming to `ARCHITECTURE_DESCRIPTION.md`.

The output must:

- describe the target system in plain language
- identify the major architectural elements required
- describe each element at the **functional type** level
- define responsibilities for each element
- capture the important interfaces and interactions between elements
- capture relevant system-wide concerns, assumptions, constraints, and open questions

## Abstraction rule

Describe elements by **role**, not by implementation choice.

Do **not** use concrete product names.

## Element rule

Architectural elements must represent **meaningful system capabilities**.
They must be large enough to matter at system-design level and small enough to have a clear responsibility.

Do not model low-level implementation artifacts as architectural elements.

## Numbering rules

Use top-level element numbering in increments of 10:

- 10
- 20
- 30
- 40

## Architecture planning rule

Use `.architecture/PLAN.md` to track architecture questions that require discussion, investigation, clarification, or explicit decision. Do not over-use this for minor decisions. Keep it for blocking architectural choices.

Use `.architecture/STATE.md` to track the currently active architecture draft, current focus, active blockers, and work log.
