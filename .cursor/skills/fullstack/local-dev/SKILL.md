---
name: local-dev
description: >-
  Boots the sandbox CRM locally with npm install and npm run dev, and reports
  the expected dev URL. Use when setting up the environment or verifying a
  feature runs on localhost.
disable-model-invocation: true
---

# Local dev

## Prerequisites

- Node.js LTS installed
- CRM repo exists at path from `repos.yaml` (+ `repos.local.yaml` overrides)

## Steps

1. Run **repo-bootstrap** to resolve the CRM path.
2. In the CRM repo root:

```bash
npm install
npm run dev
```

3. Confirm the dev server starts without errors.

## Expected URL

Default: **http://localhost:3000** (adjust if the CRM README or `package.json` specifies another port).

## Troubleshooting

| Issue | Action |
|-------|--------|
| Repo missing | Scaffold per `docs/crm-poc-scope.md` |
| Port in use | Check `package.json` scripts or env for `PORT` |
| DB errors | Ensure `.env` copied from `.env.example` if required |

## Output

Tell the user:

- Commands run
- URL to open
- Any env setup needed (`.env.example` only in repo)
