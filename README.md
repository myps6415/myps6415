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
- 👥 Previously **Data Team Lead** for 2.5 years (Scrum, mentoring, hiring, vendor coordination) before switching back to a hands-on Principal IC role
- 🔬 Came up through text mining, NLP, and sentiment analysis on Chinese-language corpora — direct context for the current LLM-augmented pipeline work
- 🎯 Bias toward **lean, observable, cost-disciplined** data stacks (BigQuery + Cloud Run Jobs + dbt) over heavy orchestrators
- 🔍 Spend equal time on data modeling and on the boring infra that keeps tokens fresh, jobs idempotent, and bills small
- 📚 Currently going deep on LLM-augmented data pipelines (sentiment / topic classification) and vector search for editorial workflows

## 🛠️ Technologies & Tools

**Languages & Query**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/-SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**Cloud & Infra (GCP)**
![GCP](https://img.shields.io/badge/-Google%20Cloud-4285F4?style=flat-square&logo=google-cloud&logoColor=white)
![BigQuery](https://img.shields.io/badge/-BigQuery-669DF6?style=flat-square&logo=googlebigquery&logoColor=white)
![Cloud Run](https://img.shields.io/badge/-Cloud%20Run-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Cloudflare Pages](https://img.shields.io/badge/-Cloudflare%20Pages-F38020?style=flat-square&logo=cloudflarepages&logoColor=white)

**Data & Modeling**
![dbt](https://img.shields.io/badge/-dbt-FF694B?style=flat-square&logo=dbt&logoColor=white)
![Looker Studio](https://img.shields.io/badge/-Looker%20Studio-4285F4?style=flat-square&logo=looker&logoColor=white)

**Also worked with**
![AWS](https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/-Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Airflow](https://img.shields.io/badge/-Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![PySpark](https://img.shields.io/badge/-PySpark-E25A1C?style=flat-square&logo=apachespark&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Apache Iceberg](https://img.shields.io/badge/-Apache%20Iceberg-2D7DD2?style=flat-square&logo=apacheiceberg&logoColor=white)
![Fluentd](https://img.shields.io/badge/-Fluentd-0E83C8?style=flat-square&logo=fluentd&logoColor=white)

<details>
<summary><b>Working with</b> — patterns and tools I reach for</summary>

- **Ingestion**: Cloud Run Jobs + Cloud Scheduler (chosen over Airflow / Composer for cost), Cloud Build CI/CD
- **Modeling**: dbt-bigquery — append-only raw ingestion, then dbt staging (views) / marts (tables) with `QUALIFY ROW_NUMBER()` dedup
- **APIs**: Meta Graph API (Facebook / Instagram), Threads API (OAuth 2.0), YouTube Data API v3
- **Secrets & auth**: GCP Secret Manager, OAuth 2.0 long-lived token refresh automation
- **LLM-augmented pipelines**: Gemini via BigQuery `AI.GENERATE` for classification (shipped), BigQuery Vector Search (planned)
- **Past production**: GKE-hosted Fluentd telemetry at high QPS, Apache Iceberg + Spark data lake, multi-cloud (AWS ↔ GCP) ETL with Ansible-driven deployment, classical ML (XGBoost / RandomForest / SVM) for user-segment prediction
- **Other**: Poetry, pytest, ruff (lint + format in CI), GitHub Actions, SendGrid / SMTP email-reporting framework

</details>

## 💼 Recent Work

**Shipped**
- **Multi-platform social ingestion** — end-to-end pipelines for **Facebook, Instagram, Threads, and YouTube** into BigQuery (15 Cloud Run Jobs on staggered Cloud Scheduler triggers, append-only + dedup-on-read for full history). Powers Looker Studio dashboards used by editorial and marketing teams. A data-quality postmortem from this pipeline: [when a missing value must be NULL, not 0 →](https://myps6415.github.io/blog/null-not-zero)
- **Threads OAuth 2.0, end-to-end** — dual-account 8-scope authorization, plus a weekly Cloud Run Job that auto-refreshes the 60-day token through Secret Manager. Upgraded the original "alert + manual re-auth" design into a fully unattended one
- **Self-serve OAuth UX for non-engineers** — pure-frontend authorization helper on Cloudflare Pages so social-team editors can grant API access without engineering hand-holding
- **Inherited pipeline rewrite** — took over a Composer + Apps Script revenue pipeline; replaced it with BigQuery External Tables + Scheduled Queries, **cutting monthly cost from ~USD$300 to under $1** with no loss of functionality
- **Orchestration decision** — explicitly skipped managed Airflow (Composer) on cost grounds; chose Cloud Scheduler + Cloud Run Jobs for the current scale, with a documented migration path to a dedicated orchestrator when the workload justifies it
- **Silent failure detection** — dbt source freshness (25h warn / 49h error) + Cloud Monitoring alerts on regex-matched job failures, so a broken upstream API or crashed job can't go undetected for days
- **Personal automation self-hosting** *(June 2026)* — Migrated a Zeabur-hosted n8n workflow (daily family-schedule alert pushed to LINE) to a 178-line stdlib Python script triggered by local OpenClaw cron, **dropping the $7.88/month bill to $0** once OpenClaw had been running long enough at home to make the hosted workflow redundant. Fixed a latent all-day-event crash bug as a side effect of the rewrite. [Full migration writeup →](https://myps6415.github.io/blog/from-n8n-zeabur-to-openclaw-local)
- **LLM-augmented data pipelines** — Gemini 2.5 Flash (via BigQuery `AI.GENERATE`) for comment sentiment and post topic classification, surfaced as `fct_comments_sentiment` / `fct_post_topics` marts that dashboards and analysts query directly; an `ai_cache` keeps on-demand inference cost flat. [How I kept the bill from scaling with users →](https://myps6415.github.io/blog/llm-in-the-warehouse)
- **GA4 web-analytics ingestion** — the group's site + app traffic pulled in through the GA4 Data API (4 Cloud Run Jobs + an `fct_ga_story` ranking mart); non-engineers grant Viewer access through a self-serve Cloudflare Pages page

**In Flight**
- 🔎 **Editorial semantic search** — evaluating BigQuery Vector Search vs. self-hosted Elasticsearch (ES → BQ embeddings) so editors can search the historical archive by meaning
- 🧹 **Migration wrap-up** — the new architecture is already producing; decommissioning the last revenue pipeline off the old Composer DAG / Apps Script

**Side Project**
- **[realping.tw](https://realping.tw)** — a Taiwan real-floor-area (實坪) property-transaction database I built solo: dbt-duckdb cleans the government open data, then one shared query core serves it as both a REST API (FastAPI) and an MCP interface (FastMCP), with API keys / usage quotas, self-serve signup, an OAuth dashboard, and a Cloudflare edge guard; a LightGBM valuation model (median error ~12%) is built and held ready for when demand shows up. Live at [api](https://api.realping.tw) / [mcp](https://mcp.realping.tw).realping.tw

## 🌱 Open Source Contributions
- **[openclaw/openclaw#87291](https://github.com/openclaw/openclaw/issues/87291)** *(Filed May 2026)* — Filed a source-level root cause for a silent 500-character truncation in OpenClaw's reply-context sanitizer: one cap covered both short metadata fields and multi-paragraph bot bodies, which clobbered tail content after idle session reset and left Telegram users with "amnesiac" bots and no error trace. Proposed splitting the body cap from the field cap; maintainers later landed a more sophisticated variant of the same split — head+tail truncation with additional ReplyChain / inline ReplyToBody coverage — in commit [`3753c5e2c8`](https://github.com/openclaw/openclaw/commit/3753c5e2c8). [Full postmortem →](https://myps6415.github.io/blog/openclaw-issue87291-postmortem)
- **[openclaw/openclaw#84890](https://github.com/openclaw/openclaw/pull/84890)** *(Merged May 2026)* — Root-caused a SIGUSR1-listener / dynamic-import deadlock that left the gateway unable to restart after in-place package upgrades. Shipped a +28 / −1 surgical fix (eager-load lifecycle runtime + listener `.catch`) backed by production logs and a live `kill -USR1` reproduction on the patched build. [Full postmortem →](https://myps6415.github.io/blog/openclaw-pr84890-postmortem)

## 📞 Connect with Me
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hsiao-yu-tung-67547a119/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:myps6415@gmail.com)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@myps6415)

