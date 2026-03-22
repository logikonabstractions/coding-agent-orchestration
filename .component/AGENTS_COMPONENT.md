# COMPONENT Workflow Contract

## Purpose

Translate **one architectural element** into a **component-level design**.

## Instruction precedence & read order
1. As specified by `AGENTS.md`
2. This file
3. `.component/COMPONENTS_DESCRIPTIONS.md`
4. `.component/PLAN.md`
5. `.component/STATE.md`
6. `.component/HISTORY.md`
7. `.architecture/ARCHITECTURE_DESCRIPTION.md` (read-only reference)

## Meta-templates

Found under `/meta_templates/.component`

| File | Role |
|------|------|
| `/meta_templates/.component/components_description_tplt.md` | Output template and deliverable for the component design |
| `/meta_templates/.component/PLAN.md` | Component-design questions, investigations, and decisions |
| `/meta_templates/.component/state_tplt.md` | Current focus, active blockers, work log |
| `/meta_templates/.component/history_tplt.md` | Resolved questions and completed component reviews |

## Scope

This mode receives **exactly one architectural element** (identified by its top-level number: 10, 20, 30...) and breaks it down into the concrete components required to implement it.

## Input requirements

The prompt must provide or reference:
- the target architectural element number (e.g. "element 10")
- access to the current `.architecture/ARCHITECTURE_DESCRIPTION.md` (or its relevant section)

If the architecture has not been reviewed/approved (status ≠ DONE in `.architecture/STATE.md`), log a warning in `.component/STATE.md` but proceed unless explicitly told to stop.

## Abstraction rules

Describe each component by **concrete role and technology**. A component is the unit of work required to implement part of the target architectural element.

The correct level of abstraction for a component (10.1, 10.2, ...) is one where:
- A specific technology (or set of technologies) is identified for implementation
- The component has a clear objective and coherent set of responsibilities
- It maps to a recognizable deliverable (a service, a schema, a configured runtime, a UI module, ...)
- It remains large enough to require multiple checkpoints to deliver (roughly the size of one or a few sprints)

For example, a component could be: "Authentication mechanism", with chosen technologies (e.g. OAuth 2.0 implemented with Passport.js, hashing with bcrypt, ...). It should not be "A social media app" (too broad) nor should it be "A sign-in form" (that would be a checkpoint to implement).

## Numbering rules

Components are numbered as sub-elements of their parent architectural element:

- Architectural element 10 → components 10.1, 10.2, ..., 10.14...
- Architectural element 20 → components 20.1, 20.2, 20.3 ...

There is no fixed upper bound on component count — use as many as relevant.

## Component planning rule

Use `.component/PLAN.md` to track component-design questions that require discussion, investigation, clarification, or explicit decision. Do not over-use this track for minor decisions. Keep it for blocking component-design choices.

## Question lifecycle

1. Create a `Comp-N.N` item in `.component/PLAN.md` with status `OPEN` or `DECISION_REQUIRED`.
2. When a response is received, append a `#### Response — Comp-N.N` block under the item (see response template in `.component/PLAN.md`).
3. Once the question is fully resolved, mark the item `RESOLVED` in `.component/PLAN.md` and summarize the exchange into `.component/HISTORY.md` under **Resolved issues**. Keep it concise — `PLAN.md` retains the full record.
