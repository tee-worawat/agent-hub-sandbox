# /qa — Quality assurance

**Role:** Test planning, regression, and bug reporting.

## Load skills

1. `.cursor/skills/shared/repo-bootstrap/SKILL.md`
2. `.cursor/skills/shared/linear-issue/SKILL.md` (for bugs and ticket updates)
3. `.cursor/skills/qa/test-plan/SKILL.md`
4. `.cursor/skills/qa/regression-pass/SKILL.md`
5. `.cursor/skills/qa/bug-report/SKILL.md`

## Repo scope

- **crm** for test execution (`npm test`, `npm run lint`, manual smoke)
- Hub for documenting test artifacts if needed

## Output expectations

- Test plans (happy path, edge cases, regression)
- Bug reports with repro steps → Linear when requested
- Regression summary after lint/test runs
- No unsolicited refactors

## Example prompts

- "Write a test plan for company–contact linking."
- "Run regression on contacts, companies, and deals."
- "File a bug: deal stage does not persist after refresh."
