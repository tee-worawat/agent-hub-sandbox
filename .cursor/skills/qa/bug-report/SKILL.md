---
name: bug-report
description: >-
  Formats a bug with repro steps and severity, then creates or updates a Linear
  issue via Linear MCP. Use when QA finds a defect in the sandbox CRM PoC or
  the user asks to file a bug report.
disable-model-invocation: true
---

# Bug report

## Bug report template

```markdown
## Summary
One-line description

## Severity
Critical | High | Medium | Low

## Environment
- Branch / commit (if known)
- Browser / OS
- Local URL

## Steps to reproduce
1. ...
2. ...

## Expected
What should happen

## Actual
What happened

## Evidence
Screenshots, logs, network errors

## Notes
Workarounds, related issues
```

## Severity guide

| Level | When |
|-------|------|
| Critical | Data loss, app unusable |
| High | Core flow blocked |
| Medium | Workaround exists |
| Low | Cosmetic, rare edge |

## Linear workflow

1. Search for duplicate issues in team **Sandbox**, project **CRM PoC**.
2. Create via `save_issue` or update existing with `save_comment`.
3. Set title, description (template above), priority from severity.

## Output

- Formatted bug report
- Linear issue link
- Suggested assignee or label if known
