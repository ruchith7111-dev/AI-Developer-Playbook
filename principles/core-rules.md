# 30 rules for AI-assisted development

These are practical habits, not guarantees. Adjust review depth to the task's risk.

## Understand before generating
1. **Name the user problem.** Explain who needs what and why.
2. **Define observable success.** Replace “make it good” with testable behavior.
3. **State constraints.** Include stack, runtime, compatibility, accessibility, and budget.
4. **Separate facts from assumptions.** Ask for unknowns instead of silent guesses.
5. **Inspect the existing project first.** Do not redesign an architecture you have not examined.
6. **Ask for a plan on multi-file work.** Review scope before implementation.

## Give useful instructions
7. **Provide relevant context.** Share the schema, error, API contract, or files that matter.
8. **Specify the output.** Ask for a patch, explanation, test plan, or review.
9. **Set boundaries.** Name files and behavior that must not change.
10. **Ask for trade-offs.** Compare the simplest viable options and limitations.
11. **Use examples for exact formats.** Show representative input and output.
12. **Maintain reusable instructions.** Remove stale or contradictory project notes.

## Build in controlled steps
13. **Make one coherent change at a time.** Small diffs are easier to review.
14. **Prefer the smallest sufficient solution.** Avoid needless frameworks and dependencies.
15. **Preserve working behavior.** Identify regression risks before changing shared code.
16. **Review dependencies.** Understand why a package is needed and whether it is maintained.
17. **Keep secrets out of prompts and source control.** Use placeholders.
18. **Use least privilege.** Give agents only the access needed for the task.

## Verify, don't assume
19. **Read important diffs.** Generated code is still your code when shipped.
20. **Run relevant tests.** Confidence in prose is not test evidence.
21. **Check edge cases.** Empty input, invalid data, network failure, and permissions matter.
22. **Verify external claims.** Check current API docs and platform behavior.
23. **Inspect data handling.** Validate input, authorize access, and avoid sensitive logs.
24. **Test failure paths.** A happy path alone is not completion.

## Learn and maintain
25. **Ask why a change works.** Understanding reduces repeated dependence.
26. **Record important decisions.** Document non-obvious architecture choices.
27. **Keep changes reversible.** Use version control and focused commits.
28. **Measure quality, not only speed.** Track defects, review time, and user outcomes.
29. **Re-test after model or prompt changes.** Outputs vary across versions.
30. **Own the release.** Humans remain accountable for correctness, privacy, and impact.

## Try it
Write a one-paragraph problem statement, three acceptance criteria, and two non-goals for a feature. Ask AI to identify missing information, but do not let it implement yet.

**Check:** another developer can understand the behavior, test success, and see constraints and unknowns.

Further reading: [OpenAI prompt engineering](https://developers.openai.com/api/docs/guides/prompt-engineering) · [GitHub Copilot prompting](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering)
