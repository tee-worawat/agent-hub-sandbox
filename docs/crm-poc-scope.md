# CRM PoC scope

Local proof-of-concept CRM for the sandbox agent hub. Single repo, single dev command.

## MVP entities

### Contacts

- CRUD (create, read, update, delete)
- Fields: name, email, phone (minimal)
- Optional link to a company

### Companies

- CRUD
- Fields: name, industry or website (minimal)
- Link one or many contacts

### Deals

- CRUD
- Pipeline stages: **Lead** → **Qualified** → **Won** / **Lost**
- Link to contact and/or company
- Stage transitions update persisted state

## Technical constraints

| Area | Choice |
|------|--------|
| Language | TypeScript |
| Structure | Single repo, one `package.json` at root |
| Dev | `npm run dev` serves UI + API |
| Persistence | SQLite **or** JSON file on disk |
| Auth | None for PoC (local only) |
| Deploy | Out of scope |

## UI (minimal)

- List views per entity
- Create / edit forms
- Simple deals pipeline (list or columns by stage)
- No design system requirement beyond readable defaults

## Out of scope

- Multi-tenant auth
- Email sync, calendar, external CRM integrations
- Production hosting or CI/CD
- Real customer PII in seed data

## Success criteria

- All three entities work end-to-end locally
- Data survives server restart
- `npm test` covers core API or CRUD paths
- Agent hub roles can implement and QA features using slash commands

## Scaffold follow-up

After this hub exists, scaffold the CRM in `codeventure-parent-hub-sandbox` using the prompt in `README.md` / `AGENTS.md`.
