# PM playbook

## Start a session

1. Open `sandbox-crm.code-workspace`.
2. Run `/pm` in chat.
3. Configure Notion and Linear MCP per `docs/mcp-setup.md`.

## Typical flow

1. **Intake** — capture requirement from stakeholder
2. **PRD** — draft and publish to Notion **Codeventure PRD** (user stories without AC)
3. **Review gate** — stakeholder approves ("green light")
4. **Linear tasks** — create epic + one issue per user story (description, diagram, Figma, AC)
5. **Status updates** — weekly or sprint summaries from Linear

## Example prompts

```
Draft a PRD for the deals pipeline MVP and save to Notion Codeventure PRD.
```

```
Green light on the contact search PRD — create Linear tasks with diagrams and AC.
```

```
Triage the Parent Hub backlog and suggest sprint order.
```

```
Weekly status update for Parent Hub PoC stakeholders.
```

## Skills loaded by `/pm`

- `shared/repo-bootstrap`
- `shared/linear-issue`
- `shared/notion-spec`
- `pm/prd-draft`
- `pm/linear-story`
- `pm/acceptance-criteria`
- `pm/status-update`
