---
name: figma-handoff
description: >-
  Pulls design context from a Figma URL via Figma MCP get_design_context and
  produces implementation notes for frontend or fullstack engineers. Use when
  the user shares a figma.com link or asks for a design handoff.
disable-model-invocation: true
---

# Figma handoff

## Config

From `repos.yaml`:

```yaml
figma:
  file_key: REPLACE_ME
  pages: [CRM, Components]
```

## When to use

- User provides a `figma.com` URL
- User references CRM or Components pages in the sandbox Figma file

## Workflow

1. Parse `fileKey` and `nodeId` from the URL (`node-id=1-2` → `1:2`).
2. Call Figma MCP `get_design_context` with fileKey and nodeId.
3. Summarize for implementers:

### Implementation notes template

- **Screen / component name**
- **Layout** — structure, spacing, breakpoints
- **Components** — map to existing CRM components where possible
- **Tokens** — colors, typography (prefer design system variables)
- **States** — hover, focus, error, empty, loading
- **Gaps** — missing assets, ambiguous interactions, API needs

4. Hand off to `frontend/ui-from-figma` or fullstack feature work as appropriate.

Do not commit Figma access tokens. Replace `REPLACE_ME` in repos.yaml locally if needed.
