# PLAN

## How to use this file

- This is the **component design discussion and investigation backlog**.
- It is **not** an implementation checkpoint plan.
- Use it to track component-level questions that require clarification, comparison, investigation, or explicit decision — typically around technology choices, trade-offs, or cross-element dependencies.
- Keep one item per question or decision.
- When a question is resolved, keep the item here for traceability, mark it `RESOLVED`, and summarize the outcome in `HISTORY.md`.

## Item format

Each item should contain:

- Type
- Status
- Target element
- Why it matters
- Known options / hypotheses
- What input or evidence is needed
- Resolution criteria
- Links to affected components or architecture sections

## Item types

- `TECH_CHOICE` — multiple viable technologies exist and a choice is needed
- `CLARIFICATION` — the architectural element is ambiguous or missing information needed for component design
- `DEPENDENCY` — a cross-element or external dependency needs resolution
- `INVESTIGATION` — more analysis or prototyping is needed before committing to a technology
- `CONSTRAINT_VALIDATION` — a technology constraint or compatibility assumption must be confirmed

## Item statuses

- `OPEN`
- `IN_PROGRESS`
- `BLOCKED`
- `DECISION_REQUIRED`
- `RESOLVED`

## Active component questions

### Comp-<element>.0 — <short title>

- Type: <TECH_CHOICE | CLARIFICATION | DEPENDENCY | INVESTIGATION | CONSTRAINT_VALIDATION>
- Status: <OPEN | IN_PROGRESS | BLOCKED | DECISION_REQUIRED | RESOLVED>
- Target element:
  - <architectural element number>
- Why it matters:
  - <why this question materially affects the component breakdown>
- Known options / hypotheses:
  - <option or hypothesis>
- Required input / evidence:
  - <what information, analysis, or human decision is needed>
- Resolution criteria:
  - <what must be true for this item to be considered resolved>
- Affected components:
  - <component IDs (e.g. 10.2, 10.5) / architecture sections / document paths>
- Notes:
  - <optional>
