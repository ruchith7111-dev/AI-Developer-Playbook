# 30 practical rules for vibe coding

Vibe coding can be useful for exploring ideas and prototyping through conversation. It becomes risky when generated code is treated as production-ready without inspection.

## Before you start
1. Describe the user and problem.
2. Choose a small first version and list exclusions.
3. State your stack and existing versions.
4. Ask the assistant to inspect the repository first.
5. Create a branch or commit before risky experiments.
6. Resolve ambiguous product decisions instead of letting AI invent them.

## While building
7. Review a plan before broad edits.
8. Build one screen, endpoint, or behavior at a time.
9. Ask for explanations of meaningful changes.
10. Request file paths and a diff summary.
11. Keep business logic separate from UI where appropriate.
12. Reject fake buttons, placeholder APIs, and demo data disguised as finished features.
13. Reuse existing conventions and components.
14. Avoid needless dependencies and rewrites.
15. Keep each task small enough to review.
16. Request loading, empty, error, and success states.
17. Use synthetic test data; do not paste private user data.
18. Stop and narrow scope if unrelated files change.

## When something breaks
19. Reproduce the issue before asking for a fix.
20. Share exact errors, logs, and reproduction steps.
21. Ask for causes ranked by evidence, not a random rewrite.
22. Test one suspected cause at a time.
23. Re-run the failing test after the fix.
24. Ask what regression the fix could introduce.

## Before shipping
25. Review authentication and authorization separately.
26. Validate on the server; client checks are not enough.
27. Review database access and ownership rules.
28. Check secrets, logs, dependencies, and exposed endpoints.
29. Test a clean environment or deployment preview.
30. Be able to explain the important code you ship.

## Example: turn a vague request into a useful one

**Vague:** “Build me a complete modern app. Make it perfect.”

**Better:** “Inspect the existing project. Do not edit files yet. Summarize the architecture, identify files likely involved in adding password reset, list unknowns and security considerations, then propose a minimal plan and wait for approval.”

The better request creates a review point; it does not guarantee correctness.

## Exercise
Rewrite “Make my dashboard better and fix everything.” Include the user goal, exact screen, current and desired behavior, constraints, non-goals, acceptance criteria, and verification steps.

Video/reading companions: [VS Code context engineering](https://code.visualstudio.com/docs/agents/guides/context-engineering-guide) · [GitHub Copilot prompt guide](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-engineering)
