# MCP setup for sandbox CRM PoC

Configure MCP servers in **Cursor Settings → MCP** (or your team’s shared MCP config). Do not commit API keys or tokens to this repo.

## Linear

**Used by:** PM, QA, Fullstack (issue linking)

| Role | Typical actions |
|------|-----------------|
| PM | Create epic + story issues from approved PRDs, status updates |
| QA | File bugs, attach repro |
| Fullstack | Comment on completion |

**Sandbox defaults** (from `repos.yaml`):

- Team: `CodeVenture`
- Project: `Parent Hub PoC`

**Auth:** Linear API key or OAuth via Cursor Linear plugin. Store credentials in Cursor settings only.

**Common tools:** `get_issue`, `save_issue`, `save_comment`, `list_issues` (check MCP tool schema before calling).

## Notion

**Used by:** PM (primary), Fullstack/Frontend (read specs)

| Role | Typical actions |
|------|-----------------|
| PM | Create/update PRDs in **Codeventure PRD** |
| Engineering | Read PRD pages before building; AC lives on Linear issues |

**Auth:** Notion integration token in Cursor MCP config — never in repo files.

**Common tools:** search workspace, query database, create/update pages.

## Figma

**Used by:** PM (link in Linear stories), Frontend, Fullstack (UI features)

| Role | Typical actions |
|------|-----------------|
| PM | Add Figma links to Linear story issues during Phase 4 |
| Frontend | `get_design_context` from handoff URLs |
| Fullstack | Same when building UI-heavy slices |

**Config:** Set `figma.file_key` in `repos.local.yaml` or replace `REPLACE_ME` locally (do not commit real keys if restricted).

**Auth:** Figma personal access token or official Figma MCP OAuth in Cursor.

## Verification checklist

- [ ] Linear: can fetch an issue from team CodeVenture
- [ ] Notion: can search workspace or query Codeventure PRD
- [ ] Figma: can open design context for a test node

## Troubleshooting

| Problem | Fix |
|---------|-----|
| MCP server offline | Restart Cursor; check MCP logs |
| 401 / auth errors | Re-authenticate in MCP settings |
| Wrong team/project | Confirm `repos.yaml` Linear section |
