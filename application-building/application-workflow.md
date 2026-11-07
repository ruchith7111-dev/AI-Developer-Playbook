# Build an application with AI: end-to-end workflow

Framework-neutral workflow. Adapt commands and files to your stack.

| Phase | Your responsibility | Useful AI task | Evidence |
|---|---|---|---|
| Discover | Define user and problem | Ask clarifying questions | Requirements, non-goals |
| Design | Choose boundaries and data flow | Compare options | Architecture decision |
| Setup | Configure repo/environment | Explain setup | Reproducible setup |
| Implement | Approve small slices | Generate focused patches | Reviewed diffs |
| Verify | Run tests and inspect | Suggest cases, diagnose | Test output |
| Release | Approve rollout | Draft checklist | Rollback notes |
| Operate | Monitor usage | Summarize safe logs/feedback | Incidents and improvements |

## Example: task creation

Requirement: a signed-in user can create a task with a title and optional due date.

Illustrative request shape:

```json
{
  "title": "Prepare project demo",
  "dueDate": "2026-12-01"
}
```

Decide date format, timezone semantics, title limits, authorization, and validation behavior before implementation.

Ask the assistant to inspect:
- Existing task model and migrations.
- Authentication/session mechanism.
- API route conventions.
- Validation and error response format.
- Existing test setup.

Implement in slices:
1. Define and validate request schema.
2. Add server-side ownership checks.
3. Persist the task.
4. Return a documented response.
5. Add success and failure tests.
6. Connect UI loading and error states.

Verify valid input, blank title, invalid date, unauthenticated request, cross-user access, and database failure. A false success response is a bug.

## Frontend checks
- Keyboard navigation and labels.
- Loading, empty, error, success states.
- Responsive behavior.
- No fake interactions or dead buttons.
- API errors shown clearly and safely.

## Backend checks
- Server-side validation and authorization.
- Safe error handling.
- Appropriate rate limits and timeouts.
- No secrets or sensitive payloads in logs.

## Database checks
- Constraints and indexes match query patterns.
- Migrations and rollback are understood.
- Ownership relationships are enforced.
- Retention, deletion, backups, and restore are considered.

A successful local run does not prove production configuration, permissions, migrations, or external services are correct.
