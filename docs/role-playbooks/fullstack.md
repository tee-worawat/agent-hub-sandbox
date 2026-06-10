# Fullstack playbook

## Start a session

1. Open `sandbox-crm.code-workspace`.
2. Run `/fullstack` in chat.
3. Confirm CRM path via repo-bootstrap (agent reads `repos.yaml`).

## Typical flow

1. Read spec (Notion) or Linear issue
2. Data model → API → UI → tests
3. `npm run dev` and `npm test`
4. Optional Linear comment with verification steps

## Example prompts

```
Implement contact CRUD per docs/crm-poc-scope.md. Use SQLite.
```

```
Add deal stage transitions API and wire the pipeline UI.
```

```
LIN-12: fix company link on contact edit and add a regression test.
```

```
Map the CRM API routes (use repo-explorer) then implement company delete.
```

## Skills loaded by `/fullstack`

- `shared/repo-bootstrap`
- `shared/linear-issue` (when relevant)
- `fullstack/ship-crm-feature`
- `fullstack/local-dev`
