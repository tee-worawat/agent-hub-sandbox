# QA playbook

## Start a session

1. Open `sandbox-crm.code-workspace`.
2. Run `/qa` in chat.
3. Ensure CRM repo is scaffolded and `npm run dev` works.

## Typical flow

1. Read AC or Linear issue
2. Write test plan
3. Run regression (lint + test + manual smoke)
4. File bugs with repro → Linear

## Example prompts

```
Write a test plan for linking contacts to companies.
```

```
Run full regression on contacts, companies, and deals.
```

```
File a bug: moving a deal to Won does not persist after refresh. Severity High.
```

```
Compare test plan for LIN-8 against current CRM implementation.
```

## Skills loaded by `/qa`

- `shared/repo-bootstrap`
- `shared/linear-issue`
- `qa/test-plan`
- `qa/regression-pass`
- `qa/bug-report`
