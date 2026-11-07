# Before deployment checklist

## Functionality
- [ ] Acceptance criteria are met.
- [ ] Critical user journeys work in a production-like environment.
- [ ] Loading, empty, error, and success states are handled.
- [ ] Accessibility and responsive behavior are checked.

## Quality
- [ ] Relevant tests pass.
- [ ] Lint, type checks, and build complete.
- [ ] Final diff is reviewed.
- [ ] No unexplained debug code or generated files remain.
- [ ] Documentation and API contracts are current.

## Security and data
- [ ] Secrets are configured in the deployment environment.
- [ ] Authorization and ownership checks are verified.
- [ ] Migrations are reviewed and backups considered.
- [ ] Sensitive data is not exposed in logs or client bundles.
- [ ] Dependencies and exposed endpoints are reviewed.

## Operations
- [ ] Environment variables and external services are configured.
- [ ] Health checks and monitoring are available.
- [ ] Error reporting avoids sensitive data.
- [ ] Rollback/recovery steps are documented.
- [ ] Someone owns post-release monitoring.

## AI-specific
- [ ] Model/API version assumptions are documented.
- [ ] Prompt/model changes have representative evaluations.
- [ ] Tool permissions and approval boundaries are tested.
- [ ] Fallback behavior exists for model/API failures.
- [ ] AI output is not trusted as authorization or validation.

Record blockers, accepted risks, approver, and rollback owner. A green build alone is not release approval.
