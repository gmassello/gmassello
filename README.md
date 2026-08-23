<h1 align="center">Germán Massello</h1>

<p align="center">
  <b>Full-stack developer working inside systems that already exist and can't stop working.</b><br>
  SDET and AI CLI tooling at Globant · Córdoba, Argentina · since 2013
</p>

<p align="center">
  <a href="https://dev.to/gmassello"><b>Blog</b></a> ·
  <a href="https://github.com/getsentry/sentry-python/pull/7226"><b>Sentry PR #7226</b></a> ·
  <a href="https://gmassello.github.io/hindsight/"><b>hindsight demo</b></a>
</p>

<p align="center">
  <img alt="focus: SDET + AI tooling" src="https://img.shields.io/badge/focus-SDET_%2B_AI_tooling-0A0A0A">
  <img alt="python" src="https://img.shields.io/badge/python-agents_·_FastAPI-3776AB?logo=python&logoColor=white">
  <img alt="rust" src="https://img.shields.io/badge/rust-CLIs-B7410E?logo=rust&logoColor=white">
  <img alt="typescript" src="https://img.shields.io/badge/typescript-React_18-3178C6?logo=typescript&logoColor=white">
  <img alt="aws" src="https://img.shields.io/badge/aws-EKS_·_Lambda_·_SAM-232F3E?logo=amazonwebservices&logoColor=white">
  <a href="https://pypi.org/project/scrape-toolkit/"><img alt="pypi scrape-toolkit" src="https://img.shields.io/badge/pypi-scrape--toolkit-006DAD?logo=pypi&logoColor=white"></a>
</p>

---

## What I work on

Two kinds of work, mostly. **Integrations** — REST, SSE streaming, MCP as a production data path with graceful fallback. And **migrations**: Bitrise → GitHub Actions, Java 8 → 11, Appium 2 → 3.5, an AWS Device Farm account move, database and file-server moves. Both share a constraint: nothing is allowed to stop working while you change it.

Lately that habit points at agents. Not chat wrappers — on-call tooling that walks real lineage, keeps memory between incidents, and can say *no precedent* instead of inventing a root cause. Contributed upstream in [getsentry/sentry-python#7226](https://github.com/getsentry/sentry-python/pull/7226), open and awaiting review, where the reported bug turned out to be the smaller of the two ([write-up](https://dev.to/gmassello/the-bug-report-was-wrong-and-that-was-the-interesting-part-328h)).

## Featured work

**[hindsight](https://github.com/gmassello/hindsight)** · [live demo](https://gmassello.github.io/hindsight/) · [video (2:33)](https://youtu.be/y04gl1faens)<br>
On-call agent for data incidents. Walks DataHub lineage to rank blast radius and root cause, writes the diagnosis back into the catalog, and remembers — the next incident starts where this one ended.

**[recall](https://github.com/gmassello/recall)** · [live](https://d2n13wfb8jv9v.cloudfront.net) · [video (2:57)](https://youtu.be/L3CkZax88dU)<br>
On-call copilot with semantic incident memory. Its memory *is* CockroachDB — distributed vector search plus a Cloud Managed MCP Server — deployed on AWS Lambda.

**[ringdown](https://github.com/gmassello/ringdown)** · [video (2:50)](https://youtu.be/WIYBWFslix4)<br>
An escalation agent that phones the pager holder and proves the acknowledgement happened. "Notification sent" proves nothing: a commitment has an owner and a clock.

## Also on the shelf

- **[dfh](https://github.com/gmassello/dfh)** — Rust CLI for AWS Device Farm: upload apps, run tests on real devices, pull artifacts, all from the terminal.
- **[mobile-inspector-cli](https://github.com/gmassello/mobile-inspector-cli)** — Inspect an Android or iOS view hierarchy without opening Appium Inspector. Pipe-friendly, regex and XPath filters, REPL.
- **[web-scraper-toolkit](https://github.com/gmassello/web-scraper-toolkit)** — Point it at a URL, say what you want off the page, get a table. Rate-limit aware, respects robots.txt. On PyPI as [`scrape-toolkit`](https://pypi.org/project/scrape-toolkit/).
- **[iris](https://github.com/gmassello/iris)** — Receipt photo to structured JSON: four interchangeable OCR engines behind one API, benchmarked on a public dataset with ground truth.
- **[adlc](https://github.com/gmassello/adlc)** — Pipeline agéntico para banca digital regulada (Hackathon IA 2026).

## Stack

**Languages** — Python · TypeScript · Java · Rust · Ruby<br>
**Frontend** — React 18 · MUI · Vite<br>
**Backend** — Node/Express · Spring · FastAPI · REST · SSE streaming · JWT<br>
**Data** — PostgreSQL · MongoDB · CockroachDB (vector indexes) · SQLite<br>
**Platform** — AWS (EKS, Lambda, SAM, RDS, S3, CloudFront) · Terraform · Backstage · GitHub Actions (OIDC keyless deploys)<br>
**AI** — LLM agents with tool use · RAG over vector search · multi-agent pipelines with human-in-the-loop gates · MCP<br>
**Testing** — Appium · Rest Assured · TestNG · TestCafe · Selenium

## Español

<details>
<summary>Misma página, en castellano</summary>

Desarrollador full-stack en Córdoba, Argentina. En Globant desde 2013; hoy SDET y herramientas CLI con IA. Trabajo casi siempre dentro de sistemas que ya existen y no pueden dejar de funcionar: **integraciones** (REST, SSE, MCP como camino de datos productivo con fallback) y **migraciones** — Bitrise → GitHub Actions, Java 8 → 11, Appium 2 → 3.5, mudanza de cuenta de AWS Device Farm, bases y file servers.

De ahí salen los proyectos de arriba: agentes de guardia que recorren linaje real, guardan memoria entre incidentes y saben decir *no hay precedente* antes de inventar una causa raíz. Contribución abierta en [getsentry/sentry-python#7226](https://github.com/getsentry/sentry-python/pull/7226).

</details>

---

<p align="center">
  <sub>Córdoba, Argentina · abierto a charlas sobre agentes, tooling y migraciones que no se pueden caer</sub>
</p>
