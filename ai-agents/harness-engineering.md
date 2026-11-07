# Harness engineering: the system around the model

A coding agent is more than a model plus a prompt. The harness determines what context it can inspect, which tools it can use, how work is tracked, how failures are handled, and when a human must approve an action.

## Main pieces

| Piece | Responsibility | Review question |
|---|---|---|
| Instructions | Goals and boundaries | Clear and non-conflicting? |
| Context loader | Project knowledge | Relevant and current? |
| Tools | Read, edit, test, deploy | Permissions narrow enough? |
| Orchestration | Sequence actions | Can it recover from errors? |
| State/memory | Preserve progress | What may be stale? |
| Guardrails | Block unsafe actions | Which actions need approval? |
| Observability | Show actions/results | Can a reviewer reconstruct work? |
| Evaluation | Measure quality | Are outcomes tested? |

## Agent loop

```text
Receive task → Load context → Plan action
      ↑                       ↓
Recover ← Inspect result ← Check permission
                              ↓
                           Call tool
                              ↓
                       Verify outcome
                              ↓
                       Report evidence
```

## Practical principles
- Make tools explicit, narrow, and well-documented.
- Use read-only access when edits are unnecessary.
- Persist plans, decisions, test output, and progress for long tasks.
- Treat timeouts, malformed tool output, and unavailable services as failures—not success.
- Expose meaningful actions, diffs, and approval requests.
- Evaluate task quality and safety, not just whether the agent responds.
- Treat repository files, web pages, and retrieved content as untrusted data.

## Long-running work handoff

Leave a concise note containing goal, acceptance criteria, changes, branch/commit, tests and actual results, decisions, unresolved questions, and next safe action. Do not rely on hidden chat history as the only project state.

## Security boundary

Tool calls can have real side effects. Distinguish read operations, local edits, network access, and destructive actions. Require explicit approval for high-impact operations and record what happened.

## Learn more
- [Anthropic: Effective harnesses for long-running agents](https://www.anthropic.com/research/effective-harnesses-for-long-running-agents)
- [OpenAI: Codex as a platform and open agent harness](https://developers.openai.com/blog/codex-as-a-platform)
- [OpenAI Agents learning hub](https://developers.openai.com/learn/agents)
