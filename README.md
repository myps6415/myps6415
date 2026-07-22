<div align="center">

# 👋 Hi, I'm John Tung (@myps6415)

### Principal Data Engineer · Modern Data Stack on GCP · OSS Contributor

⭐ **[Follow me on GitHub →](https://github.com/myps6415)**

🌐 **English** · [中文](README.zh-TW.md)

📄 **[View my CV →](https://myps6415.github.io/cv?ref=github)**

</div>

---

## 🚀 About Me
- 🌏 Based in Taiwan, working as a Principal Data Engineer at a media group
- 🛠️ Building the social analytics data platform from the ground up — ingestion, modeling, dashboards, deployment, docs
- 🧰 Production work across **GCP, AWS, and Azure**; orchestration with **Airflow**; data processing with **PySpark** — current GCP-lean stack is chosen by fit, not by habit
- 👥 Previously **Data Team Lead** for 2.5 years (Scrum, mentoring, hiring, vendor coordination) before stepping back from management to a Principal IC role — always kept building hands-on throughout
- 🔬 Came up through text mining, NLP, and sentiment analysis on Chinese-language corpora — direct context for the current LLM-augmented pipeline work
- 🎯 Bias toward **lean, observable, cost-disciplined** data stacks (BigQuery + Cloud Run Jobs + dbt) over heavy orchestrators
- 🔍 Spend equal time on data modeling and on the boring infra that keeps tokens fresh, jobs idempotent, and bills small
- 🏠 Run a homelab with the same discipline as the day job — a MacBook server hosting Docker stacks (photo backup, monitoring, a family-facing LINE AI assistant, a self-hosted agent runtime), each wrapped in its own watchdog loops
- 📚 Currently going deep on LLM-augmented data pipelines (sentiment / topic classification) and vector search for editorial workflows

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
![Looker Studio](https://img.shields.io/badge/-Looker%20Studio-4285F4?style=flat-square&logo=looker&logoColor=white)
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
- **LLM-augmented pipelines**: Gemini via BigQuery `AI.GENERATE` for classification + grounded generation (shipped), Vertex embeddings + KMEANS clustering + RAG retrieval with LLM-as-judge eval gating (shipped), BigQuery Vector Search for the editorial archive (in flight)
- **Past production**: GKE-hosted Fluentd telemetry at high QPS, Apache Iceberg + Spark data lake, multi-cloud (AWS ↔ GCP) ETL with Ansible-driven deployment, classical ML (XGBoost / RandomForest / SVM) for user-segment prediction
- **Other**: Poetry, pytest, ruff (lint + format in CI), GitHub Actions, SendGrid / SMTP email-reporting framework

</details>

## 💼 Recent Work

**Shipped**
- **Multi-platform social ingestion** — end-to-end pipelines for **Facebook, Instagram, Threads, and YouTube** into BigQuery (15+ Cloud Run Jobs on staggered Cloud Scheduler triggers, append-only + dedup-on-read for full history), with GA4 site/app traffic added on top. Powers the dashboards editorial and marketing teams open every morning. A data-quality postmortem from this pipeline: [when a missing value must be NULL, not 0 →](https://myps6415.github.io/blog/null-not-zero)
- **Two production operating dashboards** — built **two Streamlit dashboards on Cloud Run** with Google OIDC login (one for group-wide digital revenue, one for social-media performance). A self-serve **permission system** (3-tier roles + change audit) lets managers add/remove members themselves without a redeploy, and event tracking feeds product- and feature-adoption analysis. On-dashboard AI insights share a persistent cache so cost stays flat regardless of users
- **Threads OAuth 2.0, end-to-end** — dual-account 8-scope authorization, plus a weekly Cloud Run Job that auto-refreshes the 60-day token through Secret Manager. Upgraded the original "alert + manual re-auth" design into a fully unattended one
- **Self-serve OAuth UX for non-engineers** — pure-frontend authorization helper on Cloudflare Pages so social-team editors can grant API access without engineering hand-holding
- **Inherited pipeline rewrite** — took over a Composer + Apps Script revenue pipeline; replaced it with BigQuery External Tables + Scheduled Queries, **cutting monthly cost from ~USD$300 to under $1** with no loss of functionality
- **Orchestration decision** — explicitly skipped managed Airflow (Composer) on cost grounds; chose Cloud Scheduler + Cloud Run Jobs for the current scale, with a documented migration path to a dedicated orchestrator when the workload justifies it
- **Silent failure detection** — dbt source freshness (25h warn / 49h error) + Cloud Monitoring alerts on regex-matched job failures, so a broken upstream API or crashed job can't go undetected for days
- **Personal automation self-hosting** *(June 2026)* — Migrated a Zeabur-hosted n8n workflow (daily family-schedule alert pushed to LINE) to a 178-line stdlib Python script triggered by local OpenClaw cron, **dropping the $7.88/month bill to $0** once OpenClaw had been running long enough at home to make the hosted workflow redundant. Fixed a latent all-day-event crash bug as a side effect of the rewrite. [Full migration writeup →](https://myps6415.github.io/blog/from-n8n-zeabur-to-openclaw-local)
- **LINE family AI assistant + six-loop ops system** *(July 2026)* — Self-hosted LINE group bot on the home server (FastAPI webhook behind a Cloudflare Tunnel): **14 function-calling tools** — weather, quotes, FX, recurring reminders that @-mention people, price alerts gated by market hours + quote freshness (no holiday calendar to maintain), chat recap, vision, long-term memory — presented as LINE Flex cards with one-tap follow-ups, all on the free reply API and a flat-rate LLM so **marginal cost per message is $0**. Wrapped in **six independent watchdog loops running outside Docker** (liveness, daily health digest, delivery audit that catches promised-but-never-sent reminders, verified weekly backups, daily regression probes with deterministic assertions), because a webhook bot's worst failure mode is silence. [Series writeup →](https://myps6415.github.io/blog/line-bot-family-assistant)
- **This site → MDX content collections** *(June 2026)* — Migrated the blog from per-page Astro to a bilingual MDX content collection and added a self-hosted Sveltia CMS (Cloudflare Worker OAuth, $0) for browser editing. Caught two silent bugs en route — a reserved field name that nondeterministically dropped posts, and a CommonMark rule that won't bold CJK text. [Full writeup →](https://myps6415.github.io/blog/migrating-to-mdx)
- **LLM-augmented data pipelines** — Gemini 2.5 Flash (via BigQuery `AI.GENERATE`) for comment sentiment and post topic classification, surfaced as `fct_comments_sentiment` / `fct_post_topics` marts that dashboards and analysts query directly (incremental — only new rows); topic labels match the newsroom's own section taxonomy; an `ai_cache` keeps on-demand inference cost flat. [How I kept the bill from scaling with users →](https://myps6415.github.io/blog/llm-in-the-warehouse)
- **Semantic clustering + RAG retrieval foundation** — Vertex embeddings (`ML.GENERATE_EMBEDDING`, 768-dim multilingual) + KMEANS cluster negative comments, with an LLM naming each theme ("what are readers complaining about"); a comment RAG retrieval layer is gated by a **weekly LLM-as-judge eval** (two-tier thresholds; the job fails if quality drops) that guards against code regressions and model/data drift
- **Competitor benchmarking + statistical cross-BU analysis** — competitor ingestion via official public APIs (YouTube + Instagram) and topic share-of-voice; external factors (stock-market index, national business-cycle signal) joined with Mann-Kendall trend tests, Sen's slope, seasonal decomposition, and lead-lag correlation to separate tailwind growth from genuine against-the-trend wins
- **Revenue-table PDF generator** — Streamlit + ReportLab parse three TSE/OTC/EMG `.xls` files into a high-fidelity monthly-revenue newspaper-page PDF, replacing manual layout
- **GA4 web-analytics ingestion** — the group's site + app traffic pulled in through the GA4 Data API (4 Cloud Run Jobs + an `fct_ga_story` ranking mart); non-engineers grant Viewer access through a self-serve Cloudflare Pages page

**In Flight**
- 🔎 **Editorial semantic search** — the embedding + retrieval foundation is already shipped (negative-comment clustering + comment RAG retrieval); now extending it to the historical article archive, evaluating BigQuery Vector Search vs. self-hosted Elasticsearch so editors can search by meaning
- 🧹 **Migration wrap-up** — the new architecture is already producing; decommissioning the last revenue pipeline off the old Composer DAG / Apps Script

**Side Project**
- **[realping.tw](https://realping.tw)** — a Taiwan real-floor-area (實坪) property-transaction database I built solo: dbt-duckdb cleans the government open data, then one shared query core serves it as both a REST API (FastAPI) and an MCP interface (FastMCP), with API keys / usage quotas, self-serve signup, an OAuth dashboard, and a Cloudflare edge guard; a LightGBM valuation model (median error ~12%) is built and held ready for when demand shows up. Live at [api](https://api.realping.tw) / [mcp](https://mcp.realping.tw).realping.tw
- **[bopomofokids.com](https://bopomofokids.com/en)** — a free, ad-free, static React SPA teaching kids Traditional-Chinese Zhuyin (Bopomofo / ㄅㄆㄇ), grown from something my wife started for our own kid into 7 game modes. No backend, no accounts, no API keys; reading audio is real recordings from Taiwan's Ministry of Education. Caught two rendering bugs along the way that only surfaced from a different angle — one Safari-only, one only visible in an actual print preview. [Postmortem →](https://myps6415.github.io/blog/bopomofokids-rendering-bugs)

## 🌱 Open Source Contributions
- **[openclaw/openclaw#87291](https://github.com/openclaw/openclaw/issues/87291)** *(Filed May 2026)* — Filed a source-level root cause for a silent 500-character truncation in OpenClaw's reply-context sanitizer: one cap covered both short metadata fields and multi-paragraph bot bodies, which clobbered tail content after idle session reset and left Telegram users with "amnesiac" bots and no error trace. Proposed splitting the body cap from the field cap; maintainers later landed a more sophisticated variant of the same split — head+tail truncation with additional ReplyChain / inline ReplyToBody coverage — in commit [`3753c5e2c8`](https://github.com/openclaw/openclaw/commit/3753c5e2c8). [Full postmortem →](https://myps6415.github.io/blog/openclaw-issue87291-postmortem)
- **[openclaw/openclaw#84890](https://github.com/openclaw/openclaw/pull/84890)** *(Merged May 2026)* — Root-caused a SIGUSR1-listener / dynamic-import deadlock that left the gateway unable to restart after in-place package upgrades. Shipped a +28 / −1 surgical fix (eager-load lifecycle runtime + listener `.catch`) backed by production logs and a live `kill -USR1` reproduction on the patched build. [Full postmortem →](https://myps6415.github.io/blog/openclaw-pr84890-postmortem)

## 📞 Connect with Me
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hsiao-yu-tung-67547a119/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:myps6415@gmail.com)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@myps6415)

