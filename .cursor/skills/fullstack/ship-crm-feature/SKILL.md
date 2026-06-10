---
name: ship-crm-feature
description: >-
  Guides end-to-end delivery of a CRM feature from data model through API, UI,
  and tests. Use when a fullstack engineer implements contacts, companies, deals,
  or other vertical slices in the sandbox CRM PoC.
disable-model-invocation: true
---

# Ship CRM feature

## Checklist

Work in the `crm` repo only. Follow `repos-crm.mdc` conventions.

### 1. Data model

- Define types/interfaces for entities and relations
- Update persistence layer (SQLite or JSON per `docs/crm-poc-scope.md`)
- Seed or migrate test data (no real PII)

### 2. API

- Add routes under `src/server/` or `app/api/` (match scaffold)
- Validate input; return consistent error shapes
- Wire CRUD for the feature

### 3. UI

- List + create/edit forms (minimal PoC UI)
- Link entities (e.g. contact → company, deal → contact/company)
- Handle loading and error states

### 4. Tests

- Unit or integration tests for API and critical UI paths
- Run `npm test` and `npm run lint`

### 5. Linear (optional)

- If issue ID provided → `save_comment` with what shipped and how to verify

## Definition of done

- Feature works locally via `npm run dev`
- Tests pass
- No secrets committed
- User asked before any git commit
