# HospitalityIQ — Revenue Intelligence for Hotels

**Type:** Product Case Study | **Role:** PM / Builder | **Stack:** Python, OpenAI API, Streamlit, PostgreSQL

---

## The Problem

Hotel revenue managers spend 3–4 hours daily manually assembling data from 4–6 disconnected systems (PMS, OTAs, competitor scrapers). By the time they spot an anomaly, the pricing window has already passed.

**Core pains:**
- Data siloed across systems that don't talk to each other
- Revenue decisions made on yesterday's data, not real-time signals
- No early warning system for demand drops or competitor moves
- Enterprise RMS tools cost $50K+/yr — unaffordable for independent hotels

---

## Discovery: 8 Revenue Manager Interviews

| Pain Point | Frequency | Severity |
|-----------|-----------|----------|
| Manual reporting 3+ hrs/day | 8/8 | Critical |
| Missing real-time competitor signals | 7/8 | High |
| No demand anomaly early warning | 6/8 | High |
| Can't afford enterprise RMS | 5/8 | High |

**JTBD:** Make confident pricing decisions quickly, without manual data assembly.

---

## The Solution

HospitalityIQ is an AI revenue intelligence layer that aggregates data, detects anomalies automatically, and delivers daily plain-English briefings with pricing recommendations.

**v1 Feature Scope:**
- Daily AI-generated revenue briefing (email + dashboard)
- Occupancy anomaly detection (< 2hr lag vs 24–48hr manual)
- Competitor rate monitoring for top 5 comps
- Pricing recommendation with clear reasoning

---

## Success Metrics

| Metric | Baseline | Target |
|--------|----------|--------|
| Daily reporting time | 3.5 hrs | < 30 min |
| Anomaly detection lag | 24–48 hrs | < 2 hrs |


---

## 🔗 Code Repository

This case study documents the product decisions behind the HospitalityIQ automation system.

**[View Code on GitHub →](https://github.com/cloudbyharsh/Hospitality-IQ-Automation)**

The code repo includes:
- Data ingestion scripts (PMS, OTA, competitor scrapers)
- OpenAI API integration for anomaly detection
- Streamlit dashboard source
- PostgreSQL schema and migration files
