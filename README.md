## Germán Massello

Full-stack developer — Córdoba, Argentina. At Globant since 2013; today SDET and AI CLI tooling.

Most of my work happens inside systems that already exist and can't stop working: **integrations** (REST, SSE streaming, MCP as a production data path with graceful fallback) and **migrations** — Bitrise → GitHub Actions, Java 8 → 11, Appium 2 → 3.5, an AWS Device Farm account move, database and file-server migrations. That habit is roughly why the contribution below reads the way it does: the interesting part was never the patch.

### Open source

**[getsentry/sentry-python#7226](https://github.com/getsentry/sentry-python/pull/7226)** — `fix(mcp,langchain): Add mechanism to captured exceptions`

The issue said the exception `mechanism` was missing from MCP and LangChain events. It wasn't missing — it was wrong, in two separate ways. `type: "generic"` left the errors unattributed, which is what the issue describes. `handled: True` was the part nobody reported: all six MCP capture sites re-raise, so the exception reaches user code, yet Sentry counted these as handled — keeping them out of the crash-free rate and out of unhandled-issue alerts.

Coverage measured, not assumed: the six capture sites split across two mutually exclusive code paths (`mcp` v1 patches decorators, v2 installs middleware), so both versions are needed to reach all of them. Along the way: a LangChain error path (`on_tool_error`) with no test at all, and a regression I introduced myself — my helper dropped a `capture_internal_exceptions()` safety net the original code had, which inside `except ... raise` would have replaced the user's exception with the SDK's own.

[Full write-up →](https://dev.to/germn_massello_791153503/the-bug-report-was-wrong-and-that-was-the-interesting-part-328h)

### Projects

- **[hindsight](https://github.com/gmassello/hindsight)** ([live demo](https://gmassello.github.io/hindsight/)) — On-call agent for data incidents: walks DataHub lineage to rank blast radius and root cause, writes the diagnosis back into the catalog, and remembers — the next incident starts where this one ended.
- **[recall](https://github.com/gmassello/recall)** ([live](https://d2n13wfb8jv9v.cloudfront.net)) — On-call copilot with semantic incident memory: an AI agent whose memory is CockroachDB (distributed vector search + Cloud Managed MCP Server), deployed on AWS Lambda.
- **[ringdown](https://github.com/gmassello/ringdown)** — An on-call escalation agent that phones the pager holder — and proves the acknowledgement happened. "Notification sent" proves nothing: a commitment has an owner and a clock.
- **[adlc](https://github.com/gmassello/adlc)** — Pipeline agéntico para banca digital regulada.
- **[web-scraper-toolkit](https://github.com/gmassello/web-scraper-toolkit)** — Point it at a URL, say what you want off the page, get back a table. Rate-limit aware, respects `robots.txt`. On PyPI as [`scrape-toolkit`](https://pypi.org/project/scrape-toolkit/).
- **[iris](https://github.com/gmassello/iris)** — Receipt photo to structured JSON, with four interchangeable OCR engines behind one API and a reproducible benchmark on a public dataset.

### Stack

**Languages** — Python · TypeScript · Java · Rust · Ruby
**Frontend** — React 18 · MUI · Vite
**Backend** — Node/Express · Spring · FastAPI · REST · SSE streaming · JWT
**Data** — MongoDB · PostgreSQL · CockroachDB (vector indexes, semantic memory) · SQLite
**Platform** — AWS (EKS, Lambda, SAM, RDS, S3, CloudFront) · Terraform · Backstage · GitHub Actions (OIDC keyless deploys)
**AI** — LLM agents with tool use · RAG over vector search · multi-agent pipelines with human-in-the-loop gates · MCP
**Testing** — Appium · Rest Assured · TestNG · TestCafe · Selenium
