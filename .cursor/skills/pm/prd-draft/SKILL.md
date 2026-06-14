---
name: prd-draft
description: >-
  Drafts a product requirements document with problem, users, scope, and
  lightweight user stories (no acceptance criteria), then saves to Notion via
  notion-spec. Use when PM needs a PRD for a CRM PoC feature or epic. Linear
  tasks are created only after explicit PM approval.
disable-model-invocation: true
---

# PRD draft

## Inputs

- Feature or epic name
- Optional: user interviews, Linear epic, stakeholder notes, Figma references (mention only — no links required in PRD)

## PRD structure

```markdown
# [Feature] PRD

## Problem statement
What pain exists today?

## Target users
Who benefits? Primary persona for PoC.

## Goals
Measurable outcomes for this release.

## Scope (in)
Bullet list of what we will build.

## Out of scope
Explicit non-goals to prevent creep.

## User stories

| ID | Title | Summary |
|----|-------|---------|
| US-001 | [Short title] | As a [persona], I want [goal] so that [benefit]. |

Do not include acceptance criteria, diagrams, or Figma links in this table.
Those are added when creating Linear tasks after PM approval.

## Success metrics
How we know it worked (adoption, task time, error rate).

## Dependencies
Design, API, data, MCP tools.

## Timeline / phases
MVP vs follow-ups.

## Open questions
Decisions needed before build.

## Links
- Linear epic: _(filled after Phase 4)_
```

## Workflow

1. Align with `docs/crm-poc-scope.md` for MVP boundaries.
2. Draft in chat for user review.
3. Publish to Notion **Product PRD** via **notion-spec** skill.
4. **Stop** — do not create Linear issues until the user gives explicit green light.
5. After approval → hand off to **linear-story** and **linear-issue** for Phase 4.

## Output

- PRD markdown (review copy)
- Notion page URL after publish
- Reminder to review before Linear task creation
