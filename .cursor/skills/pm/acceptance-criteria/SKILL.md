---
name: acceptance-criteria
description: >-
  Generates Given/When/Then acceptance criteria for a single user story, formatted
  for embedding in a Linear issue description. Use during Phase 4 task creation
  after PRD approval — not when drafting the Notion PRD.
disable-model-invocation: true
---

# Acceptance criteria

## When to use

- During **Linear task creation** (Phase 4) after PRD approval.
- Called by **linear-story** for each user story.
- Do **not** append acceptance criteria to the Notion PRD.

## Inputs

- User story ID and summary (from approved Notion PRD)
- Optional: PRD context (scope, personas), Figma design notes

## Format

Output plain text for a fenced code block inside the Linear issue (not markdown bullets):

```
Given [concrete precondition]
When [single user or system action]
Then [observable, verifiable outcome]

Given ...
When ...
Then ...
```

Provide 3–7 criteria per story.

## Quality rules

- **Given** — concrete preconditions (data exists, user on screen X)
- **When** — single user or system action per criterion
- **Then** — verifiable result (UI text, DB state, API response)
- Avoid implementation details unless necessary for clarity
- Include negative cases where relevant

## Coverage

- Happy path for primary persona
- Validation and permission edges (if applicable)
- Persistence (refresh, restart) for CRM entities

## Output

- Plain-text AC block ready to embed in a Linear issue description
- Consumed by **linear-story** — do not publish to Notion
