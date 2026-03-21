# COMPONENT workflow contract

## Purpose

Translate **one architectural element** into a **component design**. This file further specifies `AGENTS.md` for component mode.

## Instruction precedence & read order

1. As specified by `AGENTS.md`
2. This file
3. `.component/STATE.md`
4. `.component/COMPONENTS_DESCRIPTIONS.md`
5. `.component/PLAN.md`
6. `.component/HISTORY.md`
7. `.architecture/ARCHITECTURE_DESCRIPTION.md` (read-only input reference)
8. `.architecture/STATE.md` (read-only approval/status reference)

## Scope

This layer receives **exactly one architectural element** identified by its top-level number (`10`, `20`, `30`, ...). It breaks that architectural element down into the implementation components required to build it.

If it is not clear which architectural element is being targeted, you MUST ask to confirm.

## Handoff contract

Component mode exists specifically to bridge architecture mode and vibe mode.

Its output must therefore:

- keep a clear reference to the selected parent architectural element
- define implementation components that can be worked on independently or in small groups
- provide enough implementation direction that vibe mode can derive concrete checkpoints from one or more implementation components

## Abstraction level for implementation components

Describe implementation components by **concrete role and technology** as **buildable units of work** required to implement the selected architectural element.

The correct level of abstraction for an implementation component (`10.1`, `10.2`, ...) is one where:

- a specific technology or small technology set is identified for implementation
- the component has a clear objective and coherent responsibilities
- it maps to a recognizable deliverable such as a service, schema, configured runtime, UI module, or integration boundary
- it remains large enough to require meaningful implementation effort, but small enough to support checkpoint planning in vibe mode

For example, a valid implementation component could be an authentication service with selected technologies. It should not be the whole product, and it should not be a tiny implementation task such as a single form.

## Numbering rules

Implementation components are numbered as sub-elements of their parent architectural element:

- Architectural element 10 → implementation components 10.1, 10.2, ...
- Architectural element 20 → implementation components 20.1, 20.2, ...

There is no fixed upper bound on component count. Group related implementation components only when that grouping still preserves clear ownership and a clean handoff to vibe checkpoints.

## Input requirements

The prompt must provide or reference:

- the target architectural element number, for example `element 10`
- access to the current `.architecture/ARCHITECTURE_DESCRIPTION.md`, or at least the relevant parent section

If the architecture has not been reviewed or approved (`status != DONE` in `.architecture/STATE.md`), log a warning in `.component/STATE.md` but proceed unless explicitly told to stop.

## Workflow file usage

- Use `.component/PLAN.md` to track component-design questions that require discussion, investigation, or explicit decision.
- Use `.component/STATE.md` to track active blockers, warnings, or issues that materially affect the current component design.
- Use `.component/HISTORY.md` to archive resolved questions, completed component reviews, and durable design decisions.
