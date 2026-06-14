# agent-hub-sandbox

Agent OS for the sandbox CRM proof-of-concept: rules, skills, commands, and repo map. Product code lives in the sibling **`parent-hub-sandbox`** repo.

## Prerequisites

- [Cursor](https://cursor.com) with MCP support
- Node.js LTS (for CRM app — scaffolded separately)
- Optional: Linear, Notion, Figma MCP auth (see `docs/mcp-setup.md`)

## Setup

### 1. Create the sandbox workspace

```bash
mkdir -p ~/Projects/sandbox-workspace
cd ~/Projects/sandbox-workspace
# Clone or copy agent-hub-sandbox here
# Create or clone parent-hub-sandbox as sibling folder
```

Expected layout:

```
sandbox-workspace/
├── agent-hub-sandbox/          ← this repo
└── parent-hub-sandbox/           ← CRM app (scaffold next)
```

### 2. Local path overrides (optional)

If your CRM repo is not at `../parent-hub-sandbox`:

```bash
cp repos.local.yaml.example repos.local.yaml
# Edit repos.local.yaml with your path
```

`repos.local.yaml` is gitignored.

### 3. Open the workspace

In Cursor: **File → Open Workspace from File…** → `sandbox-crm.code-workspace`

### 4. Configure MCP

Follow `docs/mcp-setup.md` for Linear, Notion, and Figma. Do not commit secrets.

### 5. Bootstrap the CRM app

The CRM is **not** included in this hub repo. In a new chat with the workspace open, run **`/fullstack`** and use the scaffold prompt in `AGENTS.md` or:

```markdown
Scaffold the sandbox CRM in `parent-hub-sandbox` per `agent-hub-sandbox/docs/crm-poc-scope.md`.

Requirements:
- TypeScript, single repo, `npm run dev` runs locally
- Contacts, Companies, Deals (pipeline stages)
- Simple persistence (SQLite or JSON file)
- Minimal UI: list + create/edit forms
- `.env.example` only; README with setup
- Follow conventions in `agent-hub-sandbox/.cursor/rules/repos-crm.mdc`

Do not modify agent-hub-sandbox unless repos.yaml paths need a fix.
Do not commit unless I ask.
```

## Day to day

| Task | Command |
|------|---------|
| Write a spec | `/pm` |
| Build a feature | `/fullstack` |
| UI from design | `/frontend` |
| Test / regression | `/qa` |

See `AGENTS.md` and `docs/role-playbooks/` for example prompts.

## Key files

| File | Purpose |
|------|---------|
| `repos.yaml` | CRM path, stack, MCP metadata |
| `sandbox-crm.code-workspace` | Multi-root Cursor workspace |
| `.cursor/rules/` | Always-on and role rules |
| `.cursor/commands/` | Slash command definitions |
| `.cursor/skills/` | Workflow playbooks per role |

## License

MIT — sandbox demo for learning and experimentation.
