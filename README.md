<div align="center">

# 👋 Hi, I'm John Tung (@myps6415)

### Data Lead · Principal Data Engineer · Data/AI platforms on GCP · OSS Contributor

⭐ **[Follow me on GitHub →](https://github.com/myps6415)**

🌐 **English** · [中文](README.zh-TW.md)

📄 **[View my CV →](https://myps6415.github.io/cv?ref=github)**

</div>

---

## 🚀 About Me
- 🌏 Based in Taoyuan, Taiwan. Data Lead / Principal Data Engineer at a media group, responsible for the data platform, the AI built on it, and the team
- 🛠️ Built the group's Data/AI platform from zero: cross-platform ingestion, dbt models, three production tools used daily by executives and editors, and generative AI with quality gates
- 🧰 Production experience on **GCP, AWS and Azure**, with **Airflow** and **PySpark**. I pick the stack by fit; right now that is mostly GCP
- 👥 Led a **four-person Data Team for two and a half years** (Scrum, mentoring, hiring, vendor work) while still writing code. I work the same way now
- 🔬 Background in Chinese text mining, NLP and sentiment analysis, which carries straight into the current LLM work
- 🎯 Prefer small, observable, low-cost stacks (BigQuery, Cloud Run Jobs, dbt) over heavy orchestrators, and spend as much time on the unglamorous parts: token refresh, idempotent jobs, small bills
- 🏠 Run a homelab on a MacBook server: Docker stacks for photo backup, monitoring, a family LINE assistant and a self-hosted agent runtime, each with its own watchdog jobs
- 📚 Currently focused on making AI reliable enough for a newsroom: grounded generation, evals that fail the job when quality drops, agents that work within explicit rules, and repo rules shared by people and AI agents

## 🛠️ Technologies & Tools

**Data Engineering**
![BigQuery](https://img.shields.io/badge/-BigQuery-669DF6?style=flat-square&logo=googlebigquery&logoColor=white)
![dbt](https://img.shields.io/badge/-dbt-FF694B?style=flat-square&logo=dbt&logoColor=white)
![Cloud Run](https://img.shields.io/badge/-Cloud%20Run%20Jobs-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Airflow](https://img.shields.io/badge/-Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![PySpark](https://img.shields.io/badge/-PySpark%20%2F%20Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white)
![Apache Iceberg](https://img.shields.io/badge/-Apache%20Iceberg-2D7DD2?style=flat-square&logo=apacheiceberg&logoColor=white)
![Fluentd](https://img.shields.io/badge/-Fluentd-0E83C8?style=flat-square&logo=fluentd&logoColor=white)

**Cloud**
![GCP](https://img.shields.io/badge/-Google%20Cloud-4285F4?style=flat-square&logo=google-cloud&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/-Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Cloudflare Pages](https://img.shields.io/badge/-Cloudflare%20Pages-F38020?style=flat-square&logo=cloudflarepages&logoColor=white)

**AI / GenAI / LLMOps**
![Gemini](https://img.shields.io/badge/-Gemini%20%2F%20Vertex%20AI-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)
![scikit-learn](https://img.shields.io/badge/-scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![LightGBM](https://img.shields.io/badge/-LightGBM-9ACD32?style=flat-square&logo=&logoColor=white)
![NLP](https://img.shields.io/badge/-Chinese%20text%20mining%20%2F%20NLP-5E8B7E?style=flat-square&logo=&logoColor=white)

**Data Analysis & Viz**
![Streamlit](https://img.shields.io/badge/-Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Superset](https://img.shields.io/badge/-Apache%20Superset-20A6C9?style=flat-square&logo=apachesuperset&logoColor=white)
![Plotly](https://img.shields.io/badge/-Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)
![pandas](https://img.shields.io/badge/-pandas-150458?style=flat-square&logo=pandas&logoColor=white)

**DevOps / CI-CD**
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Cloud Build](https://img.shields.io/badge/-Cloud%20Build-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Ansible](https://img.shields.io/badge/-Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white)
![Poetry](https://img.shields.io/badge/-Poetry-60A5FA?style=flat-square&logo=poetry&logoColor=white)
![pytest](https://img.shields.io/badge/-pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Ruff](https://img.shields.io/badge/-Ruff-D7FF64?style=flat-square&logo=ruff&logoColor=black)

**Languages & Database**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/-SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/-MySQL%20%2F%20MariaDB-4479A1?style=flat-square&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/-Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/-Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)

<details>
<summary><b>Working with</b> — patterns and tools I reach for</summary>

- **Ingestion**: Cloud Run Jobs + Cloud Scheduler (chosen over Airflow / Composer for cost), Cloud Build CI/CD
- **Modeling**: dbt-bigquery — append-only raw ingestion, then dbt staging (views) / marts (tables) with `QUALIFY ROW_NUMBER()` dedup
- **APIs**: Meta Graph API (Facebook / Instagram), Threads API (OAuth 2.0), YouTube Data API v3
- **Secrets & auth**: GCP Secret Manager, OAuth 2.0 long-lived token refresh automation
- **LLM-augmented pipelines**: Gemini via BigQuery `AI.GENERATE` for classification + grounded generation (shipped), Vertex embeddings + KMEANS clustering + RAG retrieval with LLM-as-judge eval gating (shipped), a four-tool newsroom agent with mandatory self-check, hard cost caps and weekly replay eval (shipped)
- **Past production**: GKE-hosted Fluentd telemetry at high QPS, Apache Iceberg + Spark data lake, multi-cloud (AWS ↔ GCP) ETL with Ansible-driven deployment, classical ML (XGBoost / RandomForest / SVM) for user-segment prediction
- **Other**: Poetry, pytest, ruff (lint + format in CI), GitHub Actions, SendGrid / SMTP email-reporting framework

</details>

## 💼 Recent Work

**Shipped at work**
- **Multi-platform ingestion**: Facebook, Instagram, Threads, YouTube and GA4 into BigQuery through 34 Cloud Run Jobs on staggered schedules, append-only with dedup on read. dbt source freshness, account-level checks and Cloud Monitoring catch jobs that succeed but write nothing. Postmortem: [when a missing value must be NULL, not 0 →](https://myps6415.github.io/blog/null-not-zero)
- **Three production tools for non-engineers**: a group revenue dashboard for executives, a social performance dashboard for marketing and editors, and a tool that lays out monthly revenue tables as print-ready newspaper PDFs (Streamlit + ReportLab). All run on Cloud Run behind one Google login; managers add and remove users themselves through a three-tier permission system with an audit log
- **Inherited pipeline rewrite**: replaced a Composer + Apps Script revenue pipeline with BigQuery External Tables and Scheduled Queries, **cutting monthly cost from about USD 300 to under USD 1**. At this scale Cloud Scheduler + Cloud Run Jobs does the job of a managed orchestrator; the migration path is written down for when that changes
- **Threads OAuth**: two accounts, eight scopes, and a weekly Cloud Run Job that refreshes the 60-day tokens through Secret Manager, so nobody re-authorizes by hand. Editors grant access through a static self-serve page on Cloudflare Pages
- **LLM classification in the warehouse**: Gemini 2.5 Flash through BigQuery `AI.GENERATE` classifies comment sentiment and post topics incrementally, using the newsroom's own section labels; a shared cache keeps on-demand inference cost flat. [How the bill stayed flat →](https://myps6415.github.io/blog/llm-in-the-warehouse)
- **Comment clustering and RAG**: Vertex embeddings and KMEANS group negative comments into named themes. The comment RAG layer is checked weekly by an LLM-as-judge eval that fails the job when quality drops; the third alert so far was real (duplicate comments filling the top-k) and was fixed in retrieval, not by lowering the threshold
- **Newsroom agent**: four tools (topic suggestions, viral cases, competitor radar, source-based drafting), no free-form SQL, a faithfulness check after every draft, cost caps per run and per user, and a weekly replay eval for tool choice, faithfulness and refusals
- **Competitor and cross-BU analysis**: competitor data from the official YouTube and Instagram APIs for topic share of voice, joined with the stock index and the business-cycle signal; Mann-Kendall, Sen's slope, seasonal decomposition and lead-lag correlation separate market tailwinds from real gains
- **Governance**: a data-governance inventory with an owner for each gap, cost labels on every job and service, decision records, staged onboarding, a team knowledge base, and a machine-readable repo contract (no-go zones, acceptance commands, guards) that people and AI agents both follow
- **Requirements pipeline PoC** *(Sept 2026, paused)*: a multi-agent requirements-engineering pipeline. A hook writes every user input verbatim into a hash-chained evidence log, requirements live as typed records linked by ID, and six checker agents on different models audit each round, while a deterministic validator handles the mechanical checks. In an A/B with criteria fixed before the run, interview coverage tied with the existing setup (25.9% each); the existing setup's AI auditor spent 53% of its findings on mechanical checks that the validator catches in seconds at no token cost. 147 regression tests

**Side Projects**
- **[realping.tw](https://realping.tw)**: Taiwan property transactions cleaned into comparable prices per usable area (實坪), built and run solo. dbt-duckdb builds the dataset; one query core serves a REST API (FastAPI) and an MCP server (FastMCP, **listed in the official MCP Registry**), with API keys, usage quotas, self-serve signup and Cloudflare in front. A LightGBM valuation model (median error about 12%) is built and waiting for demand. Live at [api](https://api.realping.tw) / [mcp](https://mcp.realping.tw).realping.tw
- **[bopomofokids.com](https://bopomofokids.com/en)**: a free Zhuyin (ㄅㄆㄇ) learning site for young kids that my wife started and I built out. A static React SPA with seven game modes, no backend or accounts, and Ministry of Education recordings for the readings. [Two rendering bugs, one Safari-only and one print-only →](https://myps6415.github.io/blog/bopomofokids-rendering-bugs)
- **LINE family assistant** *(July 2026)*: a self-hosted LINE group bot (FastAPI behind a Cloudflare Tunnel) with 14 function-calling tools, including weather, quotes, reminders that @-mention people and price alerts gated by market hours, at zero marginal cost per message. Six watchdog jobs run outside Docker (liveness, daily health digest, delivery audit, verified backups, regression probes), because a webhook bot usually fails silently. [Series →](https://myps6415.github.io/blog/line-bot-family-assistant)

## 🌱 Open Source Contributions
- **[apache/airflow#67592](https://github.com/apache/airflow/pull/67592)** *(Merged Oct 2026)* — My first Apache Airflow PR. After the Airflow 3 upgrade, `task.queued_duration` stopped being sent: workers now start tasks through the Execution API, and the only code that sent the metric sat on the old path. I added it back in `ti_run` (+38 / −1, plus 360 lines of tests; closes [#63503](https://github.com/apache/airflow/issues/63503) and [#66067](https://github.com/apache/airflow/issues/66067)). Most of the 4.5 months of review went into one question: when should a sample be recorded? Both guards in my first version were removed. It ended at one sample per queue wait, sent only after every step that can return a 5xx, so retries don't count twice. Merged by a PMC member, milestoned for 3.4.0. [Full write-up →](https://myps6415.github.io/blog/airflow-pr67592-queued-duration)
- **[openclaw/openclaw#87291](https://github.com/openclaw/openclaw/issues/87291)** *(Filed May 2026)* — Filed a source-level root cause for a silent 500-character truncation in OpenClaw's reply-context sanitizer: one cap covered both short metadata fields and multi-paragraph bot bodies, which clobbered tail content after idle session reset and left Telegram users with "amnesiac" bots and no error trace. Proposed splitting the body cap from the field cap; maintainers later landed a more sophisticated variant of the same split — head+tail truncation with additional ReplyChain / inline ReplyToBody coverage — in commit [`3753c5e2c8`](https://github.com/openclaw/openclaw/commit/3753c5e2c8). [Full postmortem →](https://myps6415.github.io/blog/openclaw-issue87291-postmortem)
- **[openclaw/openclaw#84890](https://github.com/openclaw/openclaw/pull/84890)** *(Merged May 2026)* — Root-caused a SIGUSR1-listener / dynamic-import deadlock that left the gateway unable to restart after in-place package upgrades. Shipped a +28 / −1 surgical fix (eager-load lifecycle runtime + listener `.catch`) backed by production logs and a live `kill -USR1` reproduction on the patched build. [Full postmortem →](https://myps6415.github.io/blog/openclaw-pr84890-postmortem)

## 📞 Connect with Me
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hsiao-yu-tung-67547a119/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:myps6415@gmail.com)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@myps6415)

