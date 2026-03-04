# HospitalityIQ Automation — Technical Overview

**Type:** Tool Built | **Stack:** Python, OpenAI API, Streamlit, PostgreSQL, APScheduler

---

## What It Does

Automates the daily revenue intelligence workflow for hotel managers — pulling data from multiple sources, running anomaly detection, and delivering a plain-English briefing every morning.

---

## Architecture

```
Data Sources          Processing Layer         Output
─────────────         ────────────────         ──────
PMS Export     →      Aggregator              →  Daily Email Briefing
OTA Reports    →      Anomaly Detector        →  Streamlit Dashboard
Comp Set Data  →      AI Summary Engine       →  Pricing Recommendations
Weather API    →      Forecast Model          →  Slack Alert (optional)
```

---

## Key Modules

### 1. Data Aggregator
- Parses CSV exports from PMS systems (Opera, Mews, Cloudbeds)
- Normalises metrics across different OTA report formats
- Stores daily snapshots in PostgreSQL for trend analysis

### 2. Anomaly Detector
- Compares current booking pace to rolling 30/60/90-day averages
- Flags when occupancy deviates > 15% from expected
- Detects sudden competitor rate drops via comp set scraper

### 3. AI Briefing Engine
- Uses OpenAI API to generate plain-English daily summary
- Structures output as: What happened → Why it matters → Recommended action
- Caches responses to control API costs

### 4. Streamlit Dashboard
- One-page view: occupancy trend, ADR, RevPAR, competitor rates
- Mobile-responsive for revenue managers on the go
- Auth handled via simple token system (upgrade path to OAuth planned)

---

## PM Decisions Made During Build

| Decision | Options Considered | Choice | Rationale |
|----------|-------------------|--------|-----------|
| Output format | Dashboard only / Email only / Both | Both | Email for daily habit; dashboard for deep dives |
| AI model | GPT-4 / GPT-3.5 / Local LLM | GPT-3.5-turbo | Cost vs quality sweet spot for briefings |
| Data storage | SQLite / PostgreSQL / No DB | PostgreSQL | Multi-property support requires relational model |
| Auth | None / API Key / OAuth | API Key (v1) | Fastest to ship; OAuth in roadmap |

---

## Running Locally

```bash
git clone https://github.com/cloudbyharsh/hospitality-iq
pip install -r requirements.txt
cp .env.example .env  # Add your OpenAI key + DB URL
python setup_db.py
streamlit run app.py
```

---

*Built by Harsh Shah | [linkedin.com/in/harshashwinshah](https://www.linkedin.com/in/harshashwinshah/)*
