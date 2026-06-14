# Agent Hub — Sandbox CRM PoC

Entry point for AI-assisted work on the local CRM proof-of-concept.

## Quick start

1. Open **`sandbox-crm.code-workspace`** in Cursor (Agent Hub + CRM folders).
2. Pick a role command: **`/pm`**, **`/fullstack`**, **`/frontend`**, **`/qa`**.
3. Agent reads **`repos.yaml`** (and optional **`repos.local.yaml`**) → works in **`parent-hub-sandbox`**.

## Repo map

| Repo | Folder | What goes here |
|------|--------|----------------|
| Hub | `agent-hub-sandbox` | Rules, skills, commands, docs |
| CRM | `parent-hub-sandbox` | App code only |

## Example prompts by role

### PM (`/pm`)

- "Draft a PRD for contact–company linking and save to Notion Product PRD."
- "Green light on the deals pipeline PRD — create Linear tasks."
- "Summarize Parent360 PoC progress from Linear this week."

### Fullstack (`/fullstack`)

- "Scaffold contact CRUD per `docs/crm-poc-scope.md`."
- "Implement deal stage transitions end-to-end with tests."
- "Fix LIN-5 and comment what you verified."

### Frontend (`/frontend`)

- "Build the deals kanban from this Figma link."
- "Improve form validation UX on the contact edit screen."

### QA (`/qa`)

- "Test plan for company CRUD and contact linking."
- "Run regression pass on all three entities."
- "File a bug for deal stage not persisting."

## Subagents

- **`repo-explorer`** — map CRM routes, components, tests (read-only)
- **`linear-triage`** — prioritize Linear backlog (read-only)

## More detail

- Architecture: `docs/architecture.md`
- MCP setup: `docs/mcp-setup.md`
- MVP scope: `docs/crm-poc-scope.md`
- Role playbooks: `docs/role-playbooks/`
