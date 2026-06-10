---
name: linear-issue
description: >-
  Fetches, creates, or updates Linear issues and comments via Linear MCP when
  the user provides a LIN-* ID or asks to file or update a ticket. Uses Sandbox
  team and CRM PoC project from repos.yaml.
disable-model-invocation: true
---

# Linear issue workflow

## When to use

- User gives `LIN-*` or a Linear URL
- User asks to create, update, or comment on a ticket

## Config

From `repos.yaml`:

```yaml
linear:
  team: Sandbox
  project: CRM PoC
```

## MCP tools

Use Linear MCP (check tool schema before calling):

- `get_issue` — fetch issue by ID or identifier
- `save_issue` — create or update issue
- `save_comment` — add comment to an issue

## Workflow

1. Bootstrap repo context if not already done.
2. If ID given → `get_issue`, summarize status, labels, assignee.
3. If creating → set team **Sandbox**, project **CRM PoC**, clear title and description.
4. If updating → preserve existing fields; only change what the user asked.
5. After implementation work → optional `save_comment` with summary and test notes.

## Output format

- Issue link and identifier
- Current status and priority
- Relevant description excerpt
- Suggested next action

Never include secrets in issue bodies or comments.
