## Germán Massello

Building AI agents for on-call and data incidents. Python, MCP, LLM tooling.

<!-- completar: rol actual, empresa, años de experiencia -->

### Open source

**[getsentry/sentry-python#7226](https://github.com/getsentry/sentry-python/pull/7226)** — `fix(mcp,langchain): Add mechanism to captured exceptions`

The issue said the exception `mechanism` was missing from MCP and LangChain events. It wasn't missing — it was wrong, in two separate ways. `type: "generic"` left the errors unattributed, which is what the issue describes. `handled: True` was the part nobody reported: all six MCP capture sites re-raise, so the exception reaches user code, yet Sentry counted these as handled — keeping them out of the crash-free rate and out of unhandled-issue alerts.

Coverage measured, not assumed: the six capture sites split across two mutually exclusive code paths (`mcp` v1 patches decorators, v2 installs middleware), so both versions are needed to reach all of them. Along the way: a LangChain error path (`on_tool_error`) with no test at all, and a regression I introduced myself — my helper dropped a `capture_internal_exceptions()` safety net the original code had, which inside `except ... raise` would have replaced the user's exception with the SDK's own.

[Full write-up →](https://dev.to/germn_massello_791153503/the-bug-report-was-wrong-and-that-was-the-interesting-part-328h)

### Projects

- **[hindsight](https://github.com/gmassello/hindsight)** — On-call agent for data incidents: walks DataHub lineage to rank blast radius and root cause, writes the diagnosis back into the catalog, and remembers — the next incident starts where this one ended.
- **[recall](https://github.com/gmassello/recall)** — On-call copilot with semantic incident memory: an AI agent whose memory is CockroachDB (distributed vector search + Cloud Managed MCP Server), deployed on AWS Lambda.
- **[adlc](https://github.com/gmassello/adlc)** — Pipeline agéntico para banca digital regulada.
- **[aiquest-minitel-client](https://github.com/gmassello/aiquest-minitel-client)** — MiniTel-Lite client for the JOSHUA infiltration challenge.

### Stack

Python · TypeScript · Rust · MCP · LLM agents
