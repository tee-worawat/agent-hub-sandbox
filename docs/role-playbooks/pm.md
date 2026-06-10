# PM playbook

## Start a session

1. Open `sandbox-crm.code-workspace`.
2. Run `/pm` in chat.
3. Configure Notion and Linear MCP per `docs/mcp-setup.md`.

## Typical flow

1. Draft PRD → Notion
2. Write Given/When/Then AC per story
3. Track execution in Linear
4. Publish status updates

## Example prompts

```
Draft a PRD for the deals pipeline MVP and save to Notion CRM Specs.
```

```
Write acceptance criteria for contact search and filter.
```

```
Triage the Sandbox CRM backlog (delegate linear-triage) and suggest sprint order.
```

```
Weekly status update for CRM PoC stakeholders.
```

## Skills loaded by `/pm`

- `shared/repo-bootstrap`
- `shared/linear-issue`
- `shared/notion-spec`
- `pm/prd-draft`
- `pm/acceptance-criteria`
- `pm/status-update`
