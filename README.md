# n8n Workflow Templates

Production-ready n8n workflows for AI automation, monitoring, and data pipelines.

## Workflows

### AI News Video Pipeline
Automated pipeline that fetches news from 13 Ukrainian and international RSS sources, deduplicates articles, filters last 24h, generates video scripts (5 Shorts + 1 long-form) using GPT-4o, saves to Notion, and notifies via Telegram.

**Stack:** Schedule Trigger → HTTP Request → XML Parser → Code (JS) → OpenAI GPT-4o → Notion → Telegram  
**Trigger:** Daily at 07:30 Kyiv time

- `WF1-News-Fetch-Scripts.json` — Fetches RSS feeds and generates scripts via GPT-4o
- `WF2-Sync-Approved-Supabase.json` — Syncs editor-approved scripts from Notion to Supabase

---

### Prozorro Tender Monitoring
Monitors Ukrainian public procurement platform (Prozorro) for relevant tenders using CPV codes and brand keywords. Filters by amount threshold, deduplicates, and sends matched tenders to Telegram.

**Stack:** Schedule Trigger → Prozorro API → Code (JS filter) → Supabase dedup → Telegram  
**API:** [public.api.openprocurement.org](https://public.api.openprocurement.org)

- `Prozorro-Tender-Monitor.json`

---

### Job Hunter
Monitors job boards (Work.ua, DOU.ua, Djinni.co) for relevant vacancies and sends them to Telegram.

**Stack:** Schedule Trigger → RSS/HTTP → AI scoring → Telegram

- `JH-RSS-API.json` — Stable version using RSS feeds and APIs
- `JH-Scraping-HTML.json` — Scraping version for boards without RSS

---

## How to import

1. Open n8n → Workflows → Import
2. Paste the JSON content or upload the file
3. Configure credentials (OpenAI, Notion, Supabase, Telegram)
4. Activate

## Author

**Mykhailo Hlovynskyi** — No-Code Automation Developer & AI Integrator

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mykhailo-hlovynskiy-34317835b/)
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=flat&logo=telegram&logoColor=white)](https://t.me/Hlovynskiy)
