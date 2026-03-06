# PLAN

## How to use this file

- This is the **component design discussion and investigation backlog**.
- It is **not** a feature implementation plan.
- Use it to track component-level questions that require clarification, comparison, investigation, or explicit decision.
- Keep one item per question or decision.
- When a question is resolved, keep the item here for traceability, mark it `RESOLVED`, and summarize the outcome in `HISTORY.md`.

## Item format

Each item should contain:

- Type
- Status
- Parent architectural component
- Why it matters
- Known options / hypotheses
- What input or evidence is needed
- Resolution criteria
- Links to affected component sections or docs

## Item types

- `CLARIFICATION` — the requested parent scope is underspecified
- `DECISION` — multiple valid implementation structures or tech choices exist and a choice is needed
- `INVESTIGATION` — more analysis is needed before selecting a component or technology
- `ASSUMPTION_VALIDATION` — an assumption must be confirmed before the design can stabilize
- `RISK_REVIEW` — a non-functional or operational risk needs explicit review

## Item statuses

- `OPEN`
- `IN_PROGRESS`
- `BLOCKED`
- `DECISION_REQUIRED`
- `RESOLVED`

## Active component design questions

### Comp-10-Q1 — <short title>

- Type: <CLARIFICATION | DECISION | INVESTIGATION | ASSUMPTION_VALIDATION | RISK_REVIEW>
- Status: <OPEN | IN_PROGRESS | BLOCKED | DECISION_REQUIRED | RESOLVED>
- Parent architectural component:
  - <10 | 20 | 30 | ...>
- Related component draft:
  - <file path or draft identifier>
- Why it matters:
  - <why this question materially affects the component design>
- Known options / hypotheses:
  - <option or hypothesis>
- Required input / evidence:
  - <what information, analysis, or human decision is needed>
- Resolution criteria:
  - <what must be true for this item to be considered resolved>
- Affected sections:
  - <component ids / sections / document paths>
- Notes:
  - <optional>
