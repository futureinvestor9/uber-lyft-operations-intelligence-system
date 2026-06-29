# Uber & Lyft Operations Intelligence System

## What This Project Is

A full-time rideshare driver operating dual platforms (Uber + Lyft) in the Chicago market
built an AI-assisted data pipeline to convert unstructured earnings history into a structured
dataset, compute KPI distributions, and deploy a tiered ride acceptance decision system.

The core problem: 80+ ride decisions per day were being made on gut feel with no baseline
data, no performance benchmarks, and no systematic way to know if the thresholds being used
were actually correct.

---

## Business Problem

- Trip history existed only as unstructured data inside the Uber and Lyft apps — no export,
  no structured format, no way to analyze without manual transcription
- Accept/reject decisions were made in a 3–5 second window with no data backing them
- No baseline existed for what $/mile or $/hour actually looked like across the full trip
  distribution
- Advantage Mode eligibility (worth ~$4,500/year) required maintaining sub-8% cancellation
  rate — but there was no system to protect it

---

## AI-Assisted Data Pipeline

![Operations Intelligence Pipeline](uber_lyft_pipeline.png)

### Input
Screen recordings of the Uber earnings feed and Mystro offer history — raw, unstructured
video showing individual trips with fare, miles, minutes, and disposition

### Process

### Output
- Clean structured dataset: fare, miles, minutes, $/mile, $/hour per trip
- KPI distributions with percentile breakdowns
- Correlation analysis proving both metrics carry independent signal
- Butterfly filter ruleset deployed in Mystro
- Block-specific decision system by time of day and day of week
- Validated blended hourly benchmark

---

## The Butterfly Filter (Decision Rules)

| Tier | Condition | Action |
|------|-----------|--------|
| Auto-accept | Above $2.00/mile AND above $35/hr | Accept immediately |
| Manual review | Between floors and ceilings | Single check: is $/mile above $2.00? |
| Auto-reject | Below $1.18/mile OR below $27/hr | Reject immediately |

Lyft floors set slightly higher due to platform market differences in Chicago.

---

## KPIs Tracked

| Metric | Value |
|--------|-------|
| All-in cost per mile (Avalon Hybrid) | $0.334/mile |
| Blended hourly rate (Uber measured) | $32.96/hr |
| Combined Uber + Lyft estimated | $35–36/hr |
| On-trip hourly range | $39–60/hr depending on window |
| Advantage Mode value protected | ~$4,500/year |
| Correlation: $/mile vs $/hour | r = 0.80 |

---

## Backtesting Method

AI-derived thresholds were validated against actual completed trips before deployment:
- Confirmed rules would have kept high-value rides
- Confirmed rules would have eliminated low-value rides
- Cross-validated $/hour targets against Uber's own measured stats screen
- Used live Lyft rejection rate (88% of 83 offers in one session) as real-time signal
  that a floor was miscalibrated

---

## High-Value Time Windows Identified

| Window | $/mile | Notes |
|--------|--------|-------|
| Saturday 1am | $4.20/mi | Highest value window |
| Friday 1am | $4.00/mi | |
| Saturday 5–8pm | $3.98/mi | Real $7.79/mi ride captured |
| Thursday 1am | $3.60/mi | |
| Any day 6am | $3.65/mi | Real $6.12/mi ride captured |

---

## Tools Used

- **Claude / ChatGPT** — Frame extraction from screen recordings, data structuring,
  threshold analysis, backtesting
- **Mystro** — Dual-platform filter deployment (Uber + Lyft simultaneous management)
- **Gridwise** — Earnings analytics and performance tracking
- **Python** — Distribution analysis, percentile computation, correlation check
- **Google Sheets** — KPI tracking and benchmark dashboard

---

## Business Translation

This pipeline is directly transferable to any operations or analytics context where:
- Data exists in unstructured or hard-to-export form
- Decisions are currently made on instinct with no baseline
- A defensible, backtested ruleset is needed instead of a guess

Applicable to: lead scoring thresholds, support ticket routing, pricing floors,
sales triage rules, inventory reorder points — any repeatable binary decision
that currently relies on experience rather than data.

---

## Skills This Project Demonstrates

`AI workflow automation` `unstructured data extraction` `KPI framework design`
`threshold backtesting` `decision rule engineering` `operations optimization`
`process documentation` `prompt engineering` `Python` `data analysis`
`business systems thinking` `Claude` `ChatGPT` `Mystro` `Gridwise`

---

## Project Status

System designed, deployed, and validated during active full-time rideshare operations
in the Chicago market. Documented here as a portfolio case study demonstrating
AI-assisted workflow design, data pipeline construction, and operations analytics.
