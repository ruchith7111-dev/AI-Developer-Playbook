# Mini-lab: build a task API with an AI assistant

**Goal:** Practice the complete loop on a small feature. Use any language/framework you know.  
**Estimated time:** 60–120 minutes.

## What you'll build

A small API that lets an authenticated user create and list their own tasks. For the first pass, use an in-memory store or local test database. Do not connect production services.

## Learning outcomes
- Write acceptance criteria before coding.
- Ask an assistant to inspect and plan.
- Implement one small slice at a time.
- Test validation and ownership boundaries.
- Review a generated diff and report evidence.

## Step 1 — Write requirements yourself

1. Create a task with a non-empty title.
2. List tasks belonging to the current test user.
3. Reject invalid input.
4. Never return another user's tasks.

Decide title length and date rules. Record assumptions.

## Step 2 — Ask for inspection

Use [the inspect template](../prompting/prompt-templates.md#1-inspect-a-codebase). Ask the assistant to identify routes, models, authentication conventions, and test tools.

**Checkpoint:** Can you explain where a request enters the app and where data is stored?

## Step 3 — Request a plan

Ask for a minimal plan with files, endpoint contracts, validation, and tests. Challenge unnecessary dependencies. Approve only a plan you understand.

## Step 4 — Implement one slice

Start with request validation and one create endpoint. Ask for a focused patch and review it before moving to list behavior.

## Step 5 — Test

| Case | Expected |
|---|---|
| Valid title | Task created |
| Missing title | Validation error |
| Whitespace-only title | Validation error |
| Unauthenticated request | Rejected |
| User A lists tasks | Only User A's tasks |
| User B lists tasks | User A's tasks are not visible |

If authentication is not implemented, inject a clearly marked test identity in the test harness. Do not pretend this is production authentication.

## Step 6 — Independent review

Use [the diff review template](../prompting/prompt-templates.md#4-review-a-diff). Focus on validation, ownership, errors, and missing tests.

## Step 7 — Write a handoff

Record what you built, files changed, tests and actual results, what is not implemented, and what production use would require.

## Completion rubric
- [ ] Requirements are clear.
- [ ] Plan reviewed.
- [ ] Main code path understood.
- [ ] Tests cover listed cases.
- [ ] Diff inspected.
- [ ] Limitations documented.

**Stretch:** Add pagination with stable ordering. Define invalid page sizes and ensure ownership filtering happens before pagination.
