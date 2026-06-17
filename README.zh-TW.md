<div align="center">

# 👋 嗨，我是 John Tung (@myps6415)

### Principal Data Engineer · GCP 現代資料堆疊 · 開源貢獻者

[![Follow @myps6415 on GitHub](https://img.shields.io/badge/Follow-%40myps6415-181717?style=social&logo=github)](https://github.com/myps6415)

🌐 [English](README.md) · **中文**

📄 **[線上 CV →](https://myps6415.github.io/zh/cv?ref=github)**

</div>

---

## 🚀 關於我
- 🌏 在台灣，於媒體集團擔任 Principal Data Engineer
- 🛠️ 從零打造社群分析資料平台 — 涵蓋資料擷取、建模、儀表板、部署、文件
- 🧰 在 **GCP、AWS、Azure** 都有正式環境經驗；排程編排用過 **Airflow**；資料處理用過 **PySpark** — 目前偏向 GCP 是出於適配考量，而非習慣
- 👥 過去曾擔任 **資料團隊 Team Lead 2.5 年**（Scrum、人員培育、招募、廠商協作），之後回到動手做的 Principal IC（個人貢獻者）角色
- 🔬 出身於中文文本探勘、NLP 與情感分析，與目前的 LLM 強化資料流工作直接接軌
- 🎯 偏好 **精簡、可觀測、成本可控** 的資料堆疊（BigQuery + Cloud Run Jobs + dbt），而非重型編排工具
- 🔍 一半時間花在資料建模，另一半花在那些不起眼但關鍵的基礎設施：讓 token 持續有效、任務具備冪等性、帳單維持精實
- 📚 目前深耕 LLM 強化資料流（情感／主題分類）以及面向編輯工作流程的向量檢索

## 🛠️ 技術與工具

**語言與查詢**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/-SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**雲端與基礎設施 (GCP)**
![GCP](https://img.shields.io/badge/-Google%20Cloud-4285F4?style=flat-square&logo=google-cloud&logoColor=white)
![BigQuery](https://img.shields.io/badge/-BigQuery-669DF6?style=flat-square&logo=googlebigquery&logoColor=white)
![Cloud Run](https://img.shields.io/badge/-Cloud%20Run-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Cloudflare Pages](https://img.shields.io/badge/-Cloudflare%20Pages-F38020?style=flat-square&logo=cloudflarepages&logoColor=white)

**資料與建模**
![dbt](https://img.shields.io/badge/-dbt-FF694B?style=flat-square&logo=dbt&logoColor=white)
![Looker Studio](https://img.shields.io/badge/-Looker%20Studio-4285F4?style=flat-square&logo=looker&logoColor=white)

**也使用過**
![AWS](https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/-Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Airflow](https://img.shields.io/badge/-Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![PySpark](https://img.shields.io/badge/-PySpark-E25A1C?style=flat-square&logo=apachespark&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Apache Iceberg](https://img.shields.io/badge/-Apache%20Iceberg-2D7DD2?style=flat-square&logo=apacheiceberg&logoColor=white)
![Fluentd](https://img.shields.io/badge/-Fluentd-0E83C8?style=flat-square&logo=fluentd&logoColor=white)

<details>
<summary><b>常用模式與工具</b> — 我習慣選用的解法</summary>

- **資料擷取**：Cloud Run Jobs + Cloud Scheduler（基於成本考量選用，而非 Airflow / Composer）、Cloud Build CI/CD
- **建模**：dbt-bigquery — raw 層 append-only ingestion，再用 dbt 建 staging（view）/ marts（table），`QUALIFY ROW_NUMBER()` 去重
- **API 串接**：Meta Graph API (Facebook / Instagram)、Threads API (OAuth 2.0)、YouTube Data API v3
- **機敏資料與授權**：GCP Secret Manager、OAuth 2.0 長效 token 自動續期
- **LLM 強化資料流**：Gemini（BigQuery `AI.GENERATE`）分類（已上線）、BigQuery Vector Search（規劃中）
- **過去正式環境經驗**：高 QPS 的 GKE Fluentd 遙測、Apache Iceberg + Spark 資料湖、跨雲 (AWS ↔ GCP) ETL 搭配 Ansible 部署、傳統 ML (XGBoost / RandomForest / SVM) 用於使用者分群預測
- **其他**：Poetry、pytest、ruff（CI lint + format）、GitHub Actions、SendGrid / SMTP 郵件報表框架

</details>

## 💼 近期工作

**已上線**
- **多平台社群資料擷取** — **Facebook、Instagram、Threads、YouTube** 端到端寫入 BigQuery 的資料流（15 個 Cloud Run Jobs 由錯峰的 Cloud Scheduler 觸發、append-only 搭配讀取時去重以保留完整歷史）。撐起編輯與行銷團隊使用的 Looker Studio 儀表板
- **Threads OAuth 2.0 全流程** — 雙帳號 8-scope 授權，搭配每週執行的 Cloud Run Job 透過 Secret Manager 自動續期 60 天有效期 token。將原本「主動通知 + 人工重新授權」的設計升級為完全免人工介入的自動化流程
- **非工程師也能自助操作的 OAuth 介面** — 部署於 Cloudflare Pages 的純前端授權輔助工具，讓社群團隊編輯不需工程師協助即可完成 API 授權
- **接手資料流重寫** — 接手既有的 Composer + Apps Script 營收資料流，改以 BigQuery External Tables + Scheduled Queries 重寫，**月成本從約 USD$300 壓到不到 $1**，功能完整保留
- **編排工具選型** — 基於成本考量明確避開 managed Airflow (Composer)，以目前規模選用 Cloud Scheduler + Cloud Run Jobs，並備妥工作負載成長後遷移至專用 orchestrator 的路徑文件
- **靜默失敗偵測** — dbt source freshness（25h warn／49h error）結合 Cloud Monitoring（regex 比對任務失敗）警示，避免上游 API 異常或任務崩潰多日無人發現
- **個人自動化自架遷移** *(2026 年 6 月)* — 把 Zeabur 上的 n8n workflow（每日家庭行程提醒推 LINE）改寫成 178 行純 stdlib Python 腳本，搭配本地 OpenClaw cron 排程，**月費從 USD$7.88 降到 $0**；本地 OpenClaw 用了一段時間後，這個託管 workflow 變得多餘。重寫的副作用是修掉一個全日事件會炸的潛在 bug。[完整遷移筆記 →](https://myps6415.github.io/zh/blog/from-n8n-zeabur-to-openclaw-local)
- **LLM 強化資料流** — 以 BigQuery 內建 Gemini 2.5 Flash（`AI.GENERATE`）處理留言情緒與貼文主題分類，產出 `fct_comments_sentiment` / `fct_post_topics` 資料市集供 dashboard 與分析師直接查；另以 `ai_cache` 把按需推論成本壓在固定低值
- **GA4 網站分析 ingestion** — 集團官網與 App 流量透過 GA4 Data API 接入（4 個 Cloud Run Jobs + 文章排行 `fct_ga_story`）；非工程師要開的「檢視者」授權走 Cloudflare Pages 自助頁

**進行中**
- 🔎 **編輯台語意搜尋** — 評估 BigQuery Vector Search 與 self-host Elasticsearch（ES → BQ embeddings），讓編輯對歷史文章做語意搜尋
- 🧹 **遷移收尾** — 新架構已出數，正把最後一條營收 pipeline 從舊的 Composer DAG / Apps Script 完全下線

**Side Project**
- **[realping.tw](https://realping.tw)** — 我獨力打造的台灣實坪房產交易資料庫：用 dbt-duckdb 清理政府開放資料，再用同一套查詢核心同時以 REST API（FastAPI）與 MCP（FastMCP）對外服務，含 API 金鑰與用量額度、自助申請、OAuth 會員後台、Cloudflare 邊緣防護；另有一個房價估價模型（LightGBM，誤差中位數約 12%）做好待需求啟用。已上線 [api](https://api.realping.tw)／[mcp](https://mcp.realping.tw).realping.tw

## 🌱 開源貢獻
- **[openclaw/openclaw#87291](https://github.com/openclaw/openclaw/issues/87291)** *(2026 年 5 月提報)* — 提交 OpenClaw 回覆上下文 sanitizer 的 500 字元靜默截斷根因：一個上限同時套用於短的 metadata 欄位與多段落的機器人回覆內文，導致閒置 session 重置後尾段內容被切除，Telegram 使用者遭遇「失憶」的機器人卻看不到任何錯誤訊息。提出將 body cap 從 field cap 拆分；maintainer 後續以更完整的變體落地相同的拆分方向 —— head+tail 截斷搭配 ReplyChain / inline ReplyToBody 路徑覆蓋，落地於 commit [`3753c5e2c8`](https://github.com/openclaw/openclaw/commit/3753c5e2c8)。[完整事後檢討 →](https://myps6415.github.io/zh/blog/openclaw-issue87291-postmortem)
- **[openclaw/openclaw#84890](https://github.com/openclaw/openclaw/pull/84890)** *(2026 年 5 月合併)* — 找出 SIGUSR1 listener 與動態 import 之間的死結，這個問題讓 gateway 在原地套件升級後無法重啟。提交 +28 / −1 的精準修復（提前載入 lifecycle runtime + listener 加上 `.catch`），佐以正式環境日誌與已修補版本上的 `kill -USR1` 重現驗證。[完整事後檢討 →](https://myps6415.github.io/zh/blog/openclaw-pr84890-postmortem)

## 📞 聯絡方式
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hsiao-yu-tung-67547a119/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:myps6415@gmail.com)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@myps6415)
