---
name: ui-from-figma
description: >-
  Implements component-level UI in the CRM repo from Figma designs, searching
  existing components first. Use after figma-handoff or when building screens
  from design references in the sandbox CRM PoC.
disable-model-invocation: true
---

# UI from Figma

## Before coding

1. Run **figma-handoff** if you have a Figma URL.
2. Search the CRM repo for existing components, layouts, and styles.
3. Prefer extending shared components over duplicating markup.

## Implementation order

1. **Structure** — page layout, sections, responsive grid
2. **Components** — buttons, inputs, tables, cards
3. **States** — empty, loading, error, success
4. **Polish** — spacing, typography, focus rings, a11y labels

## API boundaries

- If the design needs new data → document the API contract; do not silently change backend without coordination.
- Mock data is OK for UI-only passes when API is not ready.

## Quality bar

- Match design intent; use tokens/variables over hardcoded hex when available
- Keyboard navigation and form labels
- Run `npm run lint` on touched files

## Output

- List of files changed in `crm` repo
- Components created vs reused
- Any follow-ups for fullstack (API gaps)
