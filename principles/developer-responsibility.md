# Developer responsibility: what stays yours

AI can draft code, tests, docs, and plans. It cannot take accountability away from the person or organization releasing software.

| Area | AI can assist with | Developer/team must verify |
|---|---|---|
| Requirements | Draft stories and questions | Product intent and acceptance criteria |
| Architecture | Compare options | Fit, complexity, cost, maintainability |
| Code | Generate and refactor | Correctness, readability, compatibility |
| Tests | Suggest cases | Coverage of real risks and actual results |
| Security | Flag suspicious patterns | Threat model, access controls, dependency risk |
| Data | Suggest schemas and queries | Privacy, consent, retention, access |
| Deployment | Draft commands/config | Environment, rollback, monitoring |

## The explain-it-back test

Before accepting a critical change, answer:
1. What changed?
2. Which user-visible behavior changed?
3. What data does it read or write?
4. What permissions does it require?
5. What happens when an operation fails?
6. Which tests or evidence support it?
7. How would you revert it?

If you cannot answer, pause and investigate. Ask AI to teach the code, then verify the explanation against implementation and documentation.

## Scale review to risk

- **Lower risk:** formatting or isolated docs. Review the diff and output.
- **Medium risk:** UI behavior, business logic, integrations. Review diff, tests, edge cases, and compatibility.
- **Higher risk:** authentication, authorization, payments, personal data, infrastructure, destructive operations. Require focused human review, security checks, staged rollout, and rollback planning.

This is a practical heuristic, not a formal risk standard.

## Exercise
Pick one AI-generated change. Write a short review using the questions above. For each unknown, list the evidence you need.
