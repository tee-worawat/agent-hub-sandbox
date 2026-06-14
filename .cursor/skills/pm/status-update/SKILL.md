---
name: status-update
description: >-
  Pulls Linear issue status for the Parent360 PoC project and writes a short
  stakeholder summary. Use when PM needs a weekly or sprint status update.
disable-model-invocation: true
---

# Status update

## Inputs

- Time range (this week, sprint) — default: last 7 days
- Optional: audience (engineering, leadership)

## Data gathering

1. Read `repos.yaml` → `repos.crm.linear` for team and project names.
2. Use Linear MCP to list or filter issues by status, updated date, assignee.
3. Skim Notion **Product PRD** pages for major scope changes if relevant.

## Summary template

```markdown
# Parent360 PoC — Status [date]

## Highlights
- Shipped / demo-ready items
- Key decisions

## In progress
| Issue | Owner | Status | Notes |

## Blocked / risks
- ...

## Next up
- Prioritized backlog items

## Metrics (if any)
- Test pass rate, open P0/P1 count
```

## Tone

- Short paragraphs, scannable bullets
- No jargon; flag blockers early
- Do not include secrets or internal tokens

## Output

Stakeholder-ready markdown; optional paste into Notion or Slack by user request.
