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


---

## 🔗 Code Repository

**[View Code on GitHub →](https://github.com/cloudbyharsh/Hospitality-IQ-Automation)**

Explore the full source code including data ingestion modules, OpenAI integration, Streamlit dashboard, and PostgreSQL schema.
