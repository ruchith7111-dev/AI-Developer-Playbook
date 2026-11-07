# Debugging and testing AI-generated code

The fastest reliable debugging process is not “ask the model again with a longer prompt.” Reduce uncertainty using evidence.

## The debugging loop
1. **Reproduce:** confirm the failure and record exact steps.
2. **Observe:** capture error, logs, request, response, and environment.
3. **Localize:** find where behavior diverges.
4. **Hypothesize:** list likely causes and supporting evidence.
5. **Test:** confirm or reject one hypothesis.
6. **Fix:** make the smallest correction.
7. **Regress:** add a test that would have caught the bug.
8. **Verify:** rerun tests and inspect the diff.

## Example: Save spinner never stops

Do not immediately rewrite the page. Trace the request:
- Does the click handler run?
- Is the request sent?
- Is URL and method correct?
- Does the server receive it?
- Does validation reject the payload?
- Does the database operation finish?
- Does the server return a response?
- Does the client handle success and failure?
- Is loading state reset after failure?

This follows the request across boundaries and narrows the fault.

## Ask AI to help without surrendering diagnosis

```text
Here are reproduction steps and exact error output.
Trace the likely execution path. Give up to three plausible causes,
ranked by evidence. For each, say what would confirm or disprove it.
Do not change code yet.
```

## Test levels
- **Unit:** isolated functions and rules.
- **Integration:** boundaries such as API + database.
- **End-to-end:** important user journeys through the system.

Choose tests based on risk, not a test-count target.

| Category | Example |
|---|---|
| Happy path | Valid request returns expected result |
| Boundary | Empty string, max length, date boundary |
| Invalid input | Malformed JSON or unsupported file |
| Authorization | User cannot access another user's record |
| Resilience | Timeout or external service unavailable |
| Regression | Previously fixed bug stays fixed |
| UX state | Loading and error states are recoverable |

A common trap: AI writes a function and tests based on the same mistaken assumption. Both can agree and still be wrong. Derive expected behavior from requirements and independent examples, not only generated code.

## Exercise
Introduce a deliberate bug into a toy app. Reproduce it, write a failing test, fix it, and verify the regression test passes. Record the evidence.
