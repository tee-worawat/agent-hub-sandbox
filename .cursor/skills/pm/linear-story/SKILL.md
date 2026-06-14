---
name: linear-story
description: >-
  Creates one Linear issue per approved PRD user story with description, Mermaid
  diagram, optional Figma link, and Given/When/Then acceptance criteria. Use
  after explicit PM green light on a Notion PRD in Product PRD.
disable-model-invocation: true
---

# Linear story (task package)

## When to use

- User gives explicit approval on a PRD ("green light", "approved", "create tasks").
- Approved PRD exists in Notion **Product PRD**.

## Prerequisites

- Read the approved Notion PRD and extract all `US-*` rows from the user stories table.
- Confirm green light — if not given, stop and ask for approval.
- Read `repos.yaml` for Linear team, project, and optional Figma `file_key`.

## Issue mapping

- **1 Linear issue = 1 PRD user story**
- Issue title: `[US-001] Short story title` (use the PRD title column)
- Create a **parent epic** per PRD first (title = PRD feature name); set `parentId` on each story issue.

## Issue description template

Build the `description` field on `save_issue` as Markdown with these sections in order:

### 1. Description

2–4 sentences: context, persona, and expected outcome. Expand from the PRD story summary and scope.

### 2. Flow

Fenced `mermaid` code block. Use `sequenceDiagram` for API or interaction flows; use `flowchart LR` for UI navigation.

Example (sequence):

    ## Flow

    ```mermaid
    sequenceDiagram
        participant User
        participant App
        User->>App: [primary action]
        App-->>User: [observable result]
    ```

### 3. Design

Markdown link: `[Figma — Screen name](https://www.figma.com/design/...)`

Omit this section if no design exists. Resolve URL from user intake, PRD notes, or `repos.yaml` figma config.

### 4. Acceptance criteria

Fenced plain code block (not mermaid). Generate content via **acceptance-criteria** skill:

    ## Acceptance criteria

    ```
    Given [precondition]
    When [action]
    Then [observable outcome]

    Given ...
    When ...
    Then ...
    ```

### 5. Footer

    ---
    **PRD:** [Notion page title](notion-url)
    **Story ID:** US-001

## Figma links

- Add Figma URL in the **Design** section of the description.
- Also pass `links: [{ url, title: "Figma — [screen name]" }]` on `save_issue` when a design exists.

## Workflow

1. Verify explicit PM approval — refuse to create issues without it.
2. Fetch approved PRD from Notion.
3. Create parent epic via **linear-issue** (`save_issue`):
   - Title: PRD feature name
   - Description: link to Notion PRD, problem summary, list of story IDs
   - Team and project from `repos.yaml`
4. For each `US-*` in the PRD table:
   - Generate description, Mermaid diagram, and AC (via **acceptance-criteria**)
   - Create issue with `parentId` set to the epic
   - Attach Figma link if available
5. Update Notion PRD **Links** section with epic URL and issue URLs.
6. Return summary table to the user.

## Output

| Story ID | Linear ID | Title | URL |
|----------|-----------|-------|-----|
| US-001 | LIN-… | … | … |

Plus epic link and confirmation that Notion PRD links were updated.

## Quality rules

- Diagrams must reflect the story scope — not generic placeholders.
- Do not duplicate full PRD prose; the issue should be self-contained for engineering.
- Never include secrets in issue bodies.
