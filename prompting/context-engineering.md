# Context engineering: give the agent the right information

Prompt engineering shapes the request. Context engineering shapes the information available while solving it.

More context is not automatically better. Large irrelevant dumps can hide the important details. Aim for the smallest reliable set of information that changes the decision.

## Useful context

| Context | Example | Why it helps |
|---|---|---|
| Product | User roles, flows, non-goals | Prevents building the wrong feature |
| Architecture | Frontend/backend boundaries | Reduces incompatible changes |
| Code | Relevant files, interfaces, tests | Grounds work in the real project |
| Constraints | Runtime, versions, conventions | Avoids unsuitable solutions |
| Evidence | Logs, failing tests, reproduction | Supports diagnosis |
| Decisions | Chosen approach and trade-offs | Avoids repeating old debates |

## Example project map

```text
project/
├── README.md
├── docs/
│   ├── PRODUCT.md
│   ├── ARCHITECTURE.md
│   └── DECISIONS.md
├── src/
├── tests/
└── .github/
    └── copilot-instructions.md
```

This is an example, not a mandatory structure. Follow the conventions supported by your tool.

## Context-loading sequence
1. Ask the agent to inspect the repository.
2. Point it to relevant product and architecture notes.
3. Identify exact files and interfaces involved.
4. Provide current error output when debugging.
5. Ask it to state assumptions.
6. Check it has not confused stale documentation with current code.

## Example concise project instructions

```markdown
# Project guidance
- Read README.md before proposing setup changes.
- Follow existing framework and folder conventions.
- Explain before adding dependencies.
- Keep API validation on the server.
- Never commit secrets or real user data.
- Add or update tests for behavior changes.
- Report files changed and commands run.
```

Keep always-on instructions short. Put detailed architecture in supporting docs. Do not assume a Markdown link guarantees a tool has actually read the linked file.

## Practice
Give an assistant the same task twice: once with only the task sentence, once with the relevant schema, file paths, and acceptance criteria. Compare assumptions, changed files, and test quality—not just confidence.

Further reading: [VS Code context engineering guide](https://code.visualstudio.com/docs/agents/guides/context-engineering-guide) · [GitHub context engineering](https://github.blog/ai-and-ml/generative-ai/want-better-ai-outputs-try-context-engineering/)
