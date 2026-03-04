# Schema Checker — Data Quality Tool

> A lightweight Python utility that validates HospitalityIQ data ingestion against expected schemas, flags anomalies before they reach the dashboard, and alerts the team when upstream data sources change.

---

## The Problem It Solves

When you're pulling data from 5+ hospitality sources (PMS, STR, OTA APIs), schema drift is silent and deadly. A column rename in an upstream API would silently break the AI briefing — sometimes for days before anyone noticed.

I built Schema Checker to catch these issues at ingestion time, not after the PM or GM has already seen bad data.

---

## How It Works

```
Incoming Data Feed
       ↓
[Schema Validator]
  ├── Check column names vs. expected schema


---

## 🔗 Code Repository

**[View Code on GitHub →](https://github.com/cloudbyharsh/schemacheckertool)**

Explore the full source including the YAML config system, schema validation logic, and CI integration scripts.
