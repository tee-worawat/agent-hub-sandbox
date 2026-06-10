---
name: linear-issue
description: >-
  Fetches, creates, or updates Linear issues and comments via Linear MCP when
  the user provides a LIN-* ID or asks to file or update a ticket. Uses team
  and project from repos.yaml. Supports bulk story creation from approved PRDs
  via the linear-story skill.
disable-model-invocation: true
---

# Linear issue workflow

## When to use

- User gives `LIN-*` or a Linear URL
- User asks to create, update, or comment on a ticket
- Phase 4: bulk creation of story issues from an approved PRD (via **linear-story**)

## Config

Always read from `repos.yaml` → `repos.crm.linear`:

```yaml
linear:
  team: CodeVenture
  project: Parent Hub PoC
```

Do not hardcode team or project names elsewhere.

## MCP tools

Use Linear MCP (check tool schema before calling):

- `get_issue` — fetch issue by ID or identifier
- `save_issue` — create or update issue
- `save_comment` — add comment to an issue
- `list_issues` — search/filter for status updates

## Workflow

1. Bootstrap repo context if not already done.
2. If ID given → `get_issue`, summarize status, labels, assignee.
3. If creating a single issue → set team and project from `repos.yaml`, clear title and description.
4. If creating from an approved PRD → follow **linear-story** skill:
   - Require explicit PM green light before any `save_issue` calls.
   - Create epic first, then one child issue per `US-*` with `parentId`.
5. If updating → preserve existing fields; only change what the user asked.
6. After implementation work → optional `save_comment` with summary and test notes.

## Review gate

When the user asks to create tasks from a PRD:

- If approval is unclear → ask: "Please confirm green light on the PRD before I create Linear issues."
- Do not create issues during PRD draft or review phases.

## Output format

- Issue link and identifier
- Current status and priority
- Relevant description excerpt
- For bulk create: table of Story ID → Linear issue URL
- Suggested next action

Never include secrets in issue bodies or comments.
