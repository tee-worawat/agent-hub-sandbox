# Frontend playbook

## Start a session

1. Open `sandbox-crm.code-workspace`.
2. Run `/frontend` in chat.
3. Have Figma URLs ready if doing design-driven work.

## Typical flow

1. Figma handoff → implementation notes
2. Search existing CRM components
3. Build UI; flag API gaps to fullstack
4. Lint touched files

## Example prompts

```
Build the contact list and form from this Figma URL: [link]
```

```
Polish empty states on the companies page.
```

```
Match deal pipeline columns to the CRM page in Figma — reuse components first.
```

```
Add accessible labels and focus styles to all CRM forms.
```

## Skills loaded by `/frontend`

- `shared/repo-bootstrap`
- `shared/figma-handoff`
- `frontend/ui-from-figma`
