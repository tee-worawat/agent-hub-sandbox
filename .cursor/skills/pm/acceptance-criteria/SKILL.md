---
name: acceptance-criteria
description: >-
  Writes Given/When/Then acceptance criteria per user story for CRM features.
  Use when PM or engineering needs testable criteria before implementation in
  the sandbox CRM PoC.
disable-model-invocation: true
---

# Acceptance criteria

## Inputs

- User story or feature name
- Optional: PRD from Notion, Linear issue

## Format

For each story, provide 3–7 criteria in **Given / When / Then**:

```markdown
### US-001: [Story title]

**AC-1**
- **Given** [initial state]
- **When** [action]
- **Then** [observable outcome]

**AC-2**
...
```

## Quality rules

- **Given** — concrete preconditions (data exists, user on screen X)
- **When** — single user or system action
- **Then** — verifiable result (UI text, DB state, API response)
- Avoid implementation details unless necessary for clarity
- Include negative cases where relevant

## Coverage

- Happy path for primary persona
- Validation and permission edges (if applicable)
- Persistence (refresh, restart) for CRM entities

## Output

- AC block per story, ready for QA test plans
- Optional: append to Notion spec via **notion-spec**
