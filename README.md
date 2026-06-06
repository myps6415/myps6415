<div align="center">

# 👋 Hi, I'm John Tung (@myps6415)

### Principal Data Engineer · Modern Data Stack on GCP · OSS Contributor

[![Github](https://img.shields.io/github/followers/myps6415?label=Follow&style=social)](https://github.com/myps6415)

🌐 **English** · [中文](README.zh-TW.md)

</div>

---

## 🚀 About Me
- 🌏 Based in Taiwan, working as a Principal Data Engineer at a media group
- 🛠️ Building the social analytics data platform from the ground up — ingestion, modeling, dashboards, deployment, docs
- 🧰 Production work across **GCP, AWS, and Azure**; orchestration with **Airflow** and **Dagster**; data processing with **PySpark** — current GCP-lean stack is chosen by fit, not by habit
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
![Dagster](https://img.shields.io/badge/-Dagster-654FF0?style=flat-square&logo=dagster&logoColor=white)

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
- **Modeling**: dbt-bigquery, 3-tier raw / staging / marts pattern, append-only + `QUALIFY ROW_NUMBER()` dedup
- **APIs**: Meta Graph API (Facebook / Instagram), Threads API (OAuth 2.0), YouTube Data API v3
- **Secrets & auth**: GCP Secret Manager, OAuth 2.0 long-lived token refresh automation
- **LLM-augmented pipelines**: Gemini API for classification (in progress), BigQuery Vector Search (planned)
- **Past production**: GKE-hosted Fluentd telemetry at high QPS, Apache Iceberg + Spark data lake, multi-cloud (AWS ↔ GCP) ETL with Ansible-driven deployment, classical ML (XGBoost / RandomForest / SVM) for user-segment prediction
- **Other**: Poetry, pytest, ruff (lint + format in CI), GitHub Actions, SendGrid / SMTP for weekly email reports

</details>

## 💼 Recent Work

**Shipped**
- **Multi-platform social ingestion** — end-to-end pipelines for **Facebook, Instagram, Threads, and YouTube** into BigQuery (15 Cloud Run Jobs on staggered Cloud Scheduler triggers, append-only + dedup-on-read for full historical snapshots). Powers Looker Studio dashboards used by editorial and marketing teams
- **Threads OAuth 2.0, end-to-end** — dual-account 8-scope authorization, plus a weekly Cloud Run Job that auto-refreshes the 60-day token through Secret Manager. Upgraded the original "alert + manual re-auth" design into a fully unattended one
- **Self-serve OAuth UX for non-engineers** — pure-frontend authorization helper on Cloudflare Pages so social-team editors can grant API access without engineering hand-holding
- **Inherited pipeline rewrite** — took over a Composer + Apps Script revenue pipeline; replaced it with BigQuery External Tables + Scheduled Queries, **cutting monthly cost from ~USD$300 to under $1** with no loss of functionality
- **Orchestration decision** — explicitly skipped managed Airflow (Composer) on cost grounds; chose Cloud Scheduler + Cloud Run Jobs for the current scale, with a documented migration path to Dagster when the workload justifies it
- **Silent failure detection** — dbt source freshness (25h warn / 49h error) + Cloud Monitoring alerts on regex-matched job failures, so a broken upstream API or crashed job can't go undetected for days

**In Flight**
- 🧪 **LLM-augmented data pipelines** — Gemini API for comment sentiment and post topic classification, surfaced as `fct_comments_sentiment` / `fct_post_topics` marts
- 🔎 **BigQuery Vector Search** for an editorial content pipeline (ES → BQ embeddings) so editors can do semantic search over historical archives
- 📊 **GA4 / Analytics Data API** — adding a news site's web analytics; helper page shipped, waiting on the GA4 admin to grant the service account Viewer access

## 🌱 Open Source Contributions
- **[openclaw/openclaw#87291](https://github.com/openclaw/openclaw/issues/87291)** *(Filed May 2026 · fix in PR #87311)* — Diagnosed a silent 500-character truncation in OpenClaw's reply-context sanitizer (one cap shared across short metadata fields *and* multi-paragraph bot bodies), which clobbered tail content after idle session reset and left Telegram users with "amnesiac" bots and no error trace. Filed source-level root cause + a concrete split-cap diff backed by real deployment numbers; the fix PR adopts the proposed change. [Full postmortem →](https://myps6415.github.io/blog/openclaw-issue87291-postmortem)
- **[openclaw/openclaw#84890](https://github.com/openclaw/openclaw/pull/84890)** *(Merged May 2026)* — Root-caused a SIGUSR1-listener / dynamic-import deadlock that left the gateway unable to restart after in-place package upgrades. Shipped a +28 / −1 surgical fix (eager-load lifecycle runtime + listener `.catch`) backed by production logs and a live `kill -USR1` reproduction on the patched build. [Full postmortem →](https://myps6415.github.io/blog/openclaw-pr84890-postmortem)

## 📞 Connect with Me
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hsiao-yu-tung-67547a119/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:myps6415@gmail.com)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@myps6415)

