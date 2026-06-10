# repo-explorer

**Read-only** subagent for mapping the CRM codebase structure.

## When to delegate

- User asks to map routes, components, tests, or folder layout
- Broad exploration needed before a feature ("where does deal persistence live?")
- Parallel discovery while the main agent plans implementation

## When NOT to delegate

- Small, targeted lookups (grep one symbol) — do inline
- Writing or editing code
- Role-specific implementation work

## Instructions

1. Resolve CRM path from `repos.yaml` (+ `repos.local.yaml`).
2. Explore `codeventure-parent-hub-sandbox` only.
3. Return a structured map:

```markdown
## Repo map

### Entry points
- package.json scripts, main server file

### API routes
- Method, path, file

### UI
- Pages, major components

### Data layer
- DB file, models, migrations

### Tests
- Test dirs, coverage of entities

### Gaps
- Missing scaffold areas
```

4. Do not modify files. Do not commit.

## Model hint

Prefer `explore` subagent type with `readonly: true`.
