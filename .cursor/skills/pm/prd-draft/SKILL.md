---
name: prd-draft
description: >-
  Drafts a product requirements document with problem, users, scope, and success
  metrics, then saves to Notion via notion-spec. Use when PM needs a PRD for a
  CRM PoC feature or epic.
disable-model-invocation: true
---

# PRD draft

## Inputs

- Feature or epic name
- Optional: user interviews, Linear epic, stakeholder notes

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
As a … I want … so that …

## Success metrics
How we know it worked (adoption, task time, error rate).

## Dependencies
Design, API, data, MCP tools.

## Timeline / phases
MVP vs follow-ups.

## Open questions
Decisions needed before build.
```

## Workflow

1. Align with `docs/crm-poc-scope.md` for MVP boundaries.
2. Draft in chat for user review.
3. Publish to Notion **CRM Specs** via **notion-spec** skill.
4. Link related Linear issues if they exist.

## Output

- PRD markdown (review copy)
- Notion page URL after publish
