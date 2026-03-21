# ARCHITECTURE workflow contract

## Purpose

Translate a product or problem statement into an **architectural design**. This file further specifies `AGENTS.md` for architecture mode.

## Instruction precedence & read order

1. As specified by `AGENTS.md`
2. This file
3. `.architecture/STATE.md`
4. `.architecture/ARCHITECTURE_DESCRIPTION.md`
5. `.architecture/PLAN.md`
6. `.architecture/HISTORY.md`

## Scope

This layer defines the major architectural parts of the target system, the responsibility of each, how they interact, and the main system-wide concerns.

It must not define implementation strategies or concrete technology choices such as specific frameworks, databases, cloud products, or vendors.

## Core output

The deliverable is a markdown document that gives a **structured architectural breakdown** of the proposed solution in `.architecture/ARCHITECTURE_DESCRIPTION.md`.

The output must:

- describe the target system in plain language
- identify the major architectural elements required
- describe each architectural element at the **functional role** level
- define responsibilities for each architectural element
- capture the important interfaces and interactions between architectural elements
- capture relevant system-wide concerns, assumptions, constraints, and open questions
- follow the template defined in `.architecture/ARCHITECTURE_DESCRIPTION.md`
- be suitable as input for component mode, where one top-level architectural element can be selected and expanded independently

## Abstraction rule

Describe architectural elements by **role**, not by implementation choice.

Do **not** use concrete product names.

## Architectural element rule

Architectural elements must represent **meaningful system capabilities**.
They must be large enough to matter at system-design level and small enough to have a clear responsibility.

Do not model low-level implementation artifacts as architectural elements.

## Numbering rules

Use top-level architectural element numbering in increments of 10:

- 10
- 20
- 30
- 40

## Workflow file usage

- Use `.architecture/PLAN.md` to track architecture questions that require discussion, investigation, clarification, or explicit decision. Do not over-use this file for minor decisions.
- Use `.architecture/STATE.md` to track the currently active architecture draft, current focus, active blockers, and work log.
- Use `.architecture/HISTORY.md` to archive resolved questions, completed review rounds, and durable architecture decisions.
