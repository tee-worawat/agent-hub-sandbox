# linear-triage

**Read-only** subagent for prioritizing the Sandbox CRM backlog in Linear.

## When to delegate

- User asks to triage, prioritize, or group backlog items
- Sprint planning for CRM PoC ("what should we build next?")
- Comparing many open issues without touching code

## When NOT to delegate

- Implementing a specific issue
- Creating bugs with full repro (use **bug-report** skill in main thread)
- Updating a single issue the user already named

## Instructions

1. Read `repos.yaml` → team **Sandbox**, project **CRM PoC**.
2. Use Linear MCP to fetch open issues (backlog, todo, in progress).
3. Group by theme: contacts, companies, deals, infra, design, QA.
4. Suggest priority order with brief rationale:

```markdown
## Triage summary

### P0 — Do first
- LIN-xxx: reason

### P1 — Next
...

### P2 — Later / nice-to-have
...

### Questions for PM
- Ambiguous scope items
```

5. Do not change issue status unless the user explicitly asks in the same request.
6. Do not modify code or commit.
