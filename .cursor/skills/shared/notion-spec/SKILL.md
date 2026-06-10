---
name: notion-spec
description: >-
  Reads and writes CRM product specs in Notion via Notion MCP. Use when drafting
  PRDs, fetching spec pages, or syncing acceptance criteria to the CRM Specs
  database defined in repos.yaml.
disable-model-invocation: true
---

# Notion spec workflow

## Config

From `repos.yaml`:

```yaml
notion:
  database: CRM Specs
```

Placeholder database name is OK until Notion is wired up.

## MCP tools

Use Notion MCP (check tool schema before calling):

- Search workspace for pages matching feature or spec keywords
- Query **CRM Specs** database when listing or filtering specs
- Create or update pages with structured sections (see below)

## Spec page template

```markdown
# [Feature name]

## Problem
## Users
## Scope
## Out of scope
## Success metrics
## Acceptance criteria
## Open questions
```

## Workflow

1. Search or query for existing spec — avoid duplicates.
2. If updating → read current page, merge user changes, preserve links.
3. If creating → use template; link related Linear issue if provided.
4. Return Notion page URL to the user.

Never store API tokens or internal credentials in spec pages.
