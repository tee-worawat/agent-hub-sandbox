---
name: test-plan
description: >-
  Produces structured test cases for a CRM feature or Linear issue including
  happy path, edge cases, and regression scope. Use when QA needs a test plan
  before or after implementation in the sandbox CRM PoC.
disable-model-invocation: true
---

# Test plan

## Inputs

- Feature name or Linear issue (`LIN-*`)
- Optional: Notion spec link, PR description, or user story

## Gather context

1. Read acceptance criteria if available (Notion or issue).
2. Skim relevant code paths in `crm` repo if scaffolded.
3. Note entities involved: contacts, companies, deals.

## Test case template

For each scenario:

| Field | Content |
|-------|---------|
| ID | TP-001 |
| Title | Short name |
| Type | Happy / Edge / Regression |
| Preconditions | Data and state |
| Steps | Numbered actions |
| Expected | Observable outcome |
| Priority | P0 / P1 / P2 |

## Required coverage

- **Happy path** — primary user flow works end-to-end
- **Edge cases** — validation, empty lists, invalid IDs, stage transitions
- **Regression** — adjacent features still work (e.g. linking contact to company)

## Output

Markdown test plan the team can execute manually or automate later.
Optionally attach summary to Linear via **linear-issue** skill.
