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
  ├── Check data types (int, float, str, date)
  ├── Check null rates per column
  └── Check value ranges (e.g., occupancy 0–100%)
       ↓
  PASS → Pipeline continues
  FAIL → Alert logged + Slack/email notification
       ↓
[Anomaly Flagging]
  ├── Z-score outlier detection on key metrics
  ├── Week-over-week variance thresholds
  └── Missing data rate by source
       ↓
[Report Output]
  - Daily schema health log
  - Anomaly summary per source
  - Drift changelog (new/removed/renamed columns)
```

---

## Key Features

| Feature | Description |
|---|---|
| Schema versioning | Tracks expected vs actual schema per data source |
| Null rate monitoring | Alerts if >5% of rows are missing key fields |
| Outlier detection | Z-score + IQR based flagging on numeric columns |
| Drift detection | Identifies added, removed, or renamed columns |
| Alert routing | Console logs + optional Slack webhook integration |

---

## PM Decisions Behind This Tool

**Why not just use Great Expectations or Pandera?**
Both are excellent, but for a solo-built internal tool, they added overhead we didn't need. I wanted something I could hand off to a non-engineer — a simple config file that defines what "good data" looks like, no framework knowledge required.

**Why build it at all?**
After the third time a silent schema change caused incorrect occupancy data in a GM's morning briefing, I stopped treating data quality as an afterthought. This tool formalized what I was doing manually (spot-checking CSVs) into a repeatable process.

**What I'd do differently at scale:**
- Use dbt tests for warehouse-level validation
- Add a proper monitoring dashboard (Monte Carlo or elementary)
- Build alerting into the CI/CD pipeline instead of ad hoc

---

## Tech Stack

- **Python 3.11** — core logic
- **Pandas** — schema inspection and anomaly detection
- **PyYAML** — schema config files
- **Loguru** — structured logging
- **requests** — Slack webhook integration (optional)

---

## Sample Schema Config (YAML)

```yaml
# schemas/str_data.yaml
source: STR_Weekly_Report
expected_columns:
  - name: property_id
    dtype: str
    nullable: false
  - name: occupancy_rate
    dtype: float
    nullable: false
    valid_range: [0.0, 1.0]
  - name: adr
    dtype: float
    nullable: true
  - name: report_date
    dtype: date
    nullable: false
alert_on_null_rate_above: 0.05
```

---

## Running the Checker

```bash
# Validate a single source
python schema_checker.py --source str_data --file data/str_latest.csv

# Run all sources
python schema_checker.py --all

# Output drift report
python schema_checker.py --all --report drift
```

---

## Status

- [x] Core schema validation
- [x] Null rate monitoring
- [x] Outlier/anomaly flagging
- [x] Drift detection
- [ ] Web UI for schema config editing
- [ ] Integration with dbt for warehouse validation
- [ ] Automated weekly drift summary email

---

*Built by [Harsh Shah](https://www.linkedin.com/in/harshashwinshah/) | Part of the [PM Portfolio](https://github.com/cloudbyharsh/pm-portfolio)*
