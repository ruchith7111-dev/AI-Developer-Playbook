# Prompt engineering for software tasks

A useful coding prompt is a compact specification: outcome, context, constraints, requirements, output, and verification.

| Part | Include |
|---|---|
| Goal | Desired outcome, not just activity |
| Context | Relevant stack, files, current behavior, architecture |
| Constraints | What must not change; allowed tools/dependencies |
| Requirements | Expected behavior and edge cases |
| Output | Plan, patch, tests, explanation, or review |
| Verification | Commands and observable acceptance criteria |

## Vague vs actionable

**Vague:** “Add login to my app.”

**Actionable:**

> Inspect this repository and identify the current authentication approach. Do not edit files yet. I need email/password sign-in for existing users. Identify relevant routes, components, database tables, and environment variables. List security questions around password hashing, sessions, rate limiting, and authorization. Propose a minimal implementation plan and tests. Do not invent credentials or expose secrets.

This is more useful because it requests inspection, describes the user flow, and delays edits until the plan is reviewed.

## A five-turn workflow
1. **Understand:** summarize the existing code path and unknowns.
2. **Plan:** list ordered tasks, files, risks, and tests.
3. **Implement:** make one small approved change.
4. **Verify:** run tests and inspect the result.
5. **Review:** ask for a separate defect-focused review.

## Prompt checklist
- [ ] One clear outcome
- [ ] Relevant context, not a data dump
- [ ] Explicit constraints and non-goals
- [ ] Testable acceptance criteria
- [ ] Appropriate output format
- [ ] Verification instructions
- [ ] No passwords, tokens, or unnecessary personal data

## Practice
Write a prompt for CSV export in an existing dashboard. Specify columns, filename, empty-data behavior, authorization, and tests.

Further reading: [OpenAI prompt engineering](https://developers.openai.com/api/docs/guides/prompt-engineering) · [GitHub Copilot prompting](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering)
