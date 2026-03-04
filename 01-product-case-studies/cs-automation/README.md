# CS Automation — From Manual to Scalable

**Type:** Product Case Study (CS → PM Crossover) | **Role:** Builder / PM

> This project is personal. I lived this problem for 3 years before I built the solution.

---

## The Problem: CSMs Are Firefighting, Not Farming

In B2B SaaS, Customer Success Managers are supposed to drive adoption, expand accounts, and prevent churn. In reality, most of their time goes to:

- Manually pulling health data from 4–5 tools (CRM, product analytics, support tickets, billing)
- Writing the same QBR decks every quarter with slightly different numbers
- Sending "just checking in" emails because there's no signal telling them *when* to check in
- Reacting to churn notices 30 days after the customer had already decided to leave

**The core failure:** CS teams have no system to prioritize who needs attention and when. Everything is gut feel and calendar reminders.

---

## My Experience (The Discovery)

As a CSM managing 60+ accounts at a B2B SaaS company, I tracked how I actually spent my time for 3 weeks:

| Activity | Hours/Week | Value |
|----------|-----------|-------|
| Manually building health snapshots | 8 hrs | Low |
| Copying data between tools | 4 hrs | Zero |
| Proactive outreach based on signals | 2 hrs | High |
| Reactive firefighting | 6 hrs | Medium |

**Finding:** I spent 60% of my time on work a system could do. Only 10% was truly proactive.

---

## The Solution: A CS Health Scoring + Playbook Engine

I built an automated system that:

1. **Pulls signals** from product usage (login frequency, feature adoption, support tickets, NPS, contract data)
2. **Calculates a health score** (0–100) using a weighted model I designed with the CS team
3. **Triggers playbooks automatically** — risk alert → auto-draft outreach email → CSM reviews & sends
4. **Surfaces the right accounts** at the start of each day: "These 5 need attention today, here's why"

---

## The PM Thinking Behind It

### Problem Definition
> B2B SaaS CSMs spend 60%+ of their time on manual data work instead of proactive customer engagement, causing churn signals to be missed until it's too late to act.

### Hypothesis
> If CSMs get automated health signals with pre-drafted actions, they will increase proactive touches by 3x and reduce churn lag from 30 days to under 7 days.

### Health Score Model

| Signal | Weight | Rationale |
|--------|--------|-----------|
| Product login frequency | 25% | Leading indicator of engagement |
| Feature adoption depth | 20% | Stickiness indicator |
| Support ticket volume/sentiment | 20% | Satisfaction proxy |
| NPS score (last 90 days) | 15% | Direct satisfaction signal |
| Contract renewal timeline | 15% | Urgency indicator |
| Exec sponsor engagement | 5% | Relationship depth |

---

## Outcomes

- Reduced manual health-check time from 8 hrs/week to < 1 hr
- Increased proactive customer touches by 4x in the first month
- Churn detection lag dropped from ~30 days to ~5 days
- CSM team satisfaction with tooling increased from 4.1 to 7.8/10

---

## What I Learned (CS → PM Lessons)

1. **CSMs are the best PMs you're not using** — they know exactly where the product fails customers
2. **Automation should reduce cognitive load, not create it** — early versions surfaced too many alerts; had to ruthlessly prioritize the signal-to-noise ratio
3. **Adoption requires trust** — CSMs only acted on automated suggestions after seeing 3–4 accurate predictions. Designed a "why this score" explanation to build that trust faster

---

*Built by Harsh Shah | [linkedin.com/in/harshashwinshah](https://www.linkedin.com/in/harshashwinshah/)*
