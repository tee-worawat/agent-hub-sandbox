---
name: repo-bootstrap
description: >-
  Resolves CRM repo paths from repos.yaml and repos.local.yaml, verifies the
  repo exists, and prints dev commands. Use when starting a session or before
  editing product code in the sandbox CRM PoC.
disable-model-invocation: true
---

# Repo bootstrap

## Steps

1. Read `repos.yaml` from the hub root.
2. If `repos.local.yaml` exists, merge path overrides for `repos.crm`.
3. Resolve the absolute path to the CRM repo (`repos.crm.path` relative to hub root).
4. Verify the directory exists. If missing, tell the user to scaffold `codeventure-parent-hub-sandbox` first (see `docs/crm-poc-scope.md`).

## Print dev commands

From `repos.yaml` → `repos.crm.commands`:

| Command | Script |
|---------|--------|
| install | `npm install` |
| dev | `npm run dev` |
| test | `npm test` |
| lint | `npm run lint` |

## Output

Report:

- Resolved CRM path
- Whether the repo exists
- Stack from `repos.yaml`
- Linear team/project and Notion database names (for MCP context)

Do not edit hub files unless fixing a path mismatch the user requested.
