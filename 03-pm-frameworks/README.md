# PM Frameworks I Actually Use

> This isn't a textbook. These are the frameworks I've applied in real work — building HospitalityIQ, automating CS workflows, and transitioning from Customer Success into Product Management. Each one is annotated with what I learned from using it, not just what it says in theory.

---

## 1. Problem Framing Before Solutioning

**The mistake I kept making:** Jumping to "we should build X" before clearly defining what problem X actually solves.

**The discipline I built:**

Before writing any spec or solution, I force myself to answer:
1. Who specifically is experiencing this problem?
2. What are they doing today instead? (the workaround)
3. What does it cost them — in time, money, errors, or morale?
4. How often does it happen?
5. Why hasn't it been solved already?

**Example from my work:**
For HospitalityIQ, the initial instinct was "let's build a dashboard." I reframed it: GMs spend 3–4 hours manually pulling data every morning. They don't need a dashboard — they need the *answer* delivered to them. That reframe changed the entire product direction from a visualization tool to an AI-generated briefing.

---

## 2. Opportunity Sizing (Even Without Clean Data)

**When I use it:** Before committing time to build something, I want to know: is this worth it?

**My approach for internal/B2B tools:**

```
Impact Score = (Frequency × Time Saved × People Affected) / Build Effort

Example:
- Daily manual report: 1 per day
- Time per report: 3 hours
- People affected: 4 GMs per property
- Properties: 12
- Build effort: 2 weeks

= (1 × 3 × 4 × 12) / 14 days = ~10 hours saved per day of build time
```

Not precise. But directionally useful for prioritization decisions.

---

## 3. Discovery Interviews — My Personal Template

**What I do differently:** I start with their last 5 days, not their opinions.

Standard discovery questions get opinions. I want behaviours.

| Instead of asking... | I ask... |
|---|---|
| "Do you find reporting painful?" | "Walk me through your Monday morning — what's the first thing you do?" |
| "Would a dashboard help?" | "What's the last decision you made where you didn't have the data you wanted?" |
| "What features would you want?" | "If this tool disappeared tomorrow, what would break?" |

**What I listen for:**
- Workarounds (they signal real pain)
- Frequency (how often does it actually happen)
- Emotional language (frustration = priority)
- "We just don't do that" (unmet needs they've given up on)

---

## 4. Prioritization: My RICE Variant

Standard RICE (Reach × Impact × Confidence / Effort) is good but I adapt it for B2B SaaS context:

| Factor | How I define it |
|---|---|
| **Reach** | # of accounts affected (not users — accounts matter more in B2B) |
| **Impact** | Effect on key metric: retention, expansion, or time-to-value |
| **Confidence** | % certainty based on evidence: 0.5 = gut feel, 1.0 = validated with data |
| **Effort** | T-shirt sizes: S=1, M=3, L=8, XL=20 |

**What I add:** A "Strategic Alignment" multiplier (0.5–1.5x) based on whether it supports the current company goal. A technically high-RICE item that doesn't move the needle on what matters this quarter gets deprioritized.

---

## 5. Writing Specs That Engineers Actually Read

**The format I settled on after many ignored specs:**

```markdown
## Problem
One sentence. Who is experiencing what, and why it matters.

## Context
2–3 bullets. Background the team needs to understand the decision space.

## What We're Building
Clear, unambiguous description of the output. Include what's explicitly OUT OF SCOPE.

## Success Looks Like
2–3 measurable outcomes. "Users feel better" is not a success metric.

## Open Questions
Things we haven't decided yet. Surfacing ambiguity early prevents rework.

## Edge Cases
Scenarios that could break the happy path. Forces upfront thinking.
```

**Why this works:** Engineers hate reading long prose PRDs. This format respects their time and signals that I've done the thinking before scheduling the kickoff.

---

## 6. The CS → PM Translation Layer

Coming from Customer Success, I had to learn to translate my instincts into PM language.

| CS Instinct | PM Translation |
|---|---|
| "Customers keep asking for this" | Map to frequency data + revenue impact |
| "This is confusing customers" | User research finding + UX debt item |
| "We lose deals over this" | Competitive gap + revenue at risk |
| "Onboarding takes too long" | Time-to-value metric + churn risk signal |
| "The team is overwhelmed" | Operational cost + capacity constraint |

The skill isn't new — it's repackaging observed reality into a format that drives decisions.

---

## 7. Measuring What You Built

**The question I ask after every launch:**
*Did this actually change behaviour, or just give people a new option they ignored?*

For internal tools, I track:
- **Adoption rate:** % of target users using it within 30 days
- **Frequency:** Are they using it daily/weekly as designed?
- **Displacement:** Did it actually replace the old workaround?
- **Error rate:** Did it reduce the mistakes it was meant to prevent?

**Lesson from HospitalityIQ:**
We built the tool. GMs had it. But usage was inconsistent. Discovery revealed they were still pulling manual reports "just to double-check." The tool hadn't earned their trust yet. That led us to add explainability features — showing sources and confidence levels alongside the AI summary.

---

*Built by [Harsh Shah](https://www.linkedin.com/in/harshashwinshah/) | Part of the [PM Portfolio](https://github.com/cloudbyharsh/pm-portfolio)*
