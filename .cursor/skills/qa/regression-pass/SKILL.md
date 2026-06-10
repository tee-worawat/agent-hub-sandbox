---
name: regression-pass
description: >-
  Runs lint and tests in the CRM repo and executes a manual smoke checklist for
  contacts, companies, and deals. Use when QA needs a regression pass before
  release or after a large change in the sandbox CRM PoC.
disable-model-invocation: true
---

# Regression pass

## Automated checks

In the CRM repo root (path from **repo-bootstrap**):

```bash
npm run lint
npm test
```

Record pass/fail and relevant error output.

## Manual smoke checklist

### Contacts

- [ ] List loads
- [ ] Create contact
- [ ] Edit contact
- [ ] Delete contact (if supported)

### Companies

- [ ] List loads
- [ ] Create company
- [ ] Link contact to company
- [ ] Edit / delete company

### Deals

- [ ] Pipeline view loads
- [ ] Create deal in **Lead**
- [ ] Move through **Qualified** → **Won** or **Lost**
- [ ] Deal persists after page refresh

## Environment

- Dev server: `npm run dev` at http://localhost:3000 (or README port)
- Use fake test data only

## Output

Regression report:

1. Automated results (lint, test)
2. Manual checklist with pass/fail per item
3. Blockers and recommended Linear issues for failures
