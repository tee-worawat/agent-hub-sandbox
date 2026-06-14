---
name: notion-spec
description: >-
  Reads and writes CRM product specs in Notion via Notion MCP. Use when drafting
  PRDs, fetching spec pages, or updating links after Linear task creation. Uses
  the Product PRD database defined in repos.yaml.
disable-model-invocation: true
---

# Notion spec workflow

## Config

From `repos.yaml`:

```yaml
notion:
  database: Product PRD
```

## MCP tools

Use Notion MCP (check tool schema before calling):

- Search workspace for pages matching feature or spec keywords
- Query **Product PRD** database when listing or filtering specs
- Create or update pages with structured sections (see below)

## PRD page template

```markdown
# [Feature name]

## Problem
## Users
## Scope
## Out of scope
## User stories

| ID | Title | Summary |
|----|-------|---------|
| US-001 | … | As a … I want … so that … |

## Success metrics
## Open questions

## Links
- Linear epic: _(filled after task creation)_
- Linear issues: _(filled after task creation)_
```

Do **not** include acceptance criteria, diagrams, or Figma links on PRD pages.
Those belong on Linear issues (see **linear-story** skill).

## Workflow

1. Search or query for existing spec — avoid duplicates.
2. If updating → read current page, merge user changes, preserve links.
3. If creating → use PRD template; set status to Draft if the database has a Status property.
4. After Linear task creation → update **Links** with epic and issue URLs.
5. Return Notion page URL to the user.

Never store API tokens or internal credentials in spec pages.
