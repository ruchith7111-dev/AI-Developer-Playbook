# Security review checklist

A practical starting point, not a substitute for threat modeling or a professional security review.

## Input and output
- [ ] Validate input on the server.
- [ ] Enforce type, size, length, and format limits.
- [ ] Encode output for its destination.
- [ ] Avoid unsafe dynamic SQL, shell commands, and HTML rendering.
- [ ] Treat uploads and retrieved content as untrusted.

## Identity and access
- [ ] Authentication is enforced on protected routes.
- [ ] Authorization is checked for each resource/action.
- [ ] Users cannot access another user's records by changing an ID.
- [ ] Admin/service permissions are narrow.
- [ ] Session and token handling follows current framework guidance.

## Secrets and data
- [ ] Secrets are outside source control.
- [ ] Logs do not expose tokens, passwords, or sensitive payloads.
- [ ] Sensitive data collection is minimized.
- [ ] Retention and deletion behavior is understood.
- [ ] Database and object-storage policies are reviewed.

## AI-specific risks
- [ ] Model output is treated as untrusted input.
- [ ] Tool calls have narrow permissions and validated arguments.
- [ ] Retrieved documents cannot override application policy.
- [ ] Prompt injection and data-exfiltration paths are considered.
- [ ] Human approval exists for high-impact actions.
- [ ] AI-generated code and dependencies receive normal review.

## Operations
- [ ] Dependencies and known vulnerabilities are checked.
- [ ] Errors do not leak internals.
- [ ] Rate limits and abuse controls are appropriate.
- [ ] Monitoring and incident response are defined.

References: [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) · [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/) · [GitHub code security](https://docs.github.com/en/code-security)
