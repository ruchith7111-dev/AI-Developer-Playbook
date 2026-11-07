# Copy-ready prompt templates

Replace bracketed placeholders. Remove irrelevant sections. Never paste secrets or private data.

## 1. Inspect a codebase

```text
Inspect this repository before making changes.
Goal: [outcome]
Constraints: [stack, versions, files/behavior that must not change]
1. Summarize relevant architecture.
2. Identify likely files and interfaces.
3. List assumptions and missing information.
4. Identify risks and regression possibilities.
5. Suggest the smallest reasonable plan.
Do not edit files yet. Wait for approval.
```

## 2. Implement one feature slice

```text
Implement only: [specific behavior].
Follow existing project conventions. Do not rewrite unrelated code or add dependencies without explaining why.

Acceptance criteria:
- [observable behavior]
- [edge/error behavior]

Add or update tests. Run relevant checks if available.
Report files changed, commands run, actual results, and anything not verified.
Do not claim a check passed unless it was run.
```

## 3. Debug with evidence

```text
Investigate this bug; do not rewrite the feature immediately.
Expected: [behavior]
Actual: [behavior]
Reproduction: [steps]
Exact error/logs: [evidence]
Relevant files: [paths]
Rank likely causes by evidence. For each, explain how to confirm or reject it.
Then propose the smallest fix and a regression test.
```

## 4. Review a diff

```text
Review the current diff. Prioritize correctness, security, data loss,
authorization, regressions, and missing tests.

For each finding include severity, confidence, exact file/location,
impact, a failure scenario, and a suggested correction.
Do not report style preferences as bugs. Do not rewrite the code.
If no issues are found, state what remains unverified.
```

## 5. Build a test plan

```text
Create a test plan for [feature].
Cover success, invalid and boundary inputs, empty data, permissions,
network/timeouts, and regressions.
For each test give setup, action, expected result, and test level
(unit, integration, or end-to-end). Inspect existing test tools first.
```

## 6. Explain unfamiliar code

```text
Teach me how [file/module/function] works.
Explain responsibility, inputs/outputs, dependencies, data flow,
side effects, error handling, and one realistic example.
Use the actual code as evidence and label any inference.
```

## 7. Release readiness

```text
Review [feature/version] for configuration, migrations, secrets,
access control, validation, tests, logging, monitoring, and rollback.
Separate confirmed checks from items needing human/external review.
Do not deploy or perform destructive actions. Return blockers and risks.
```

## Improve a template
Keep only parts that materially improve results. If an assistant repeatedly misses a project convention, add it to project context rather than making every prompt longer.
