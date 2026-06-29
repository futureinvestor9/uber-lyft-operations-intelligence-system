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

### Input
Screen recordings of the Uber earnings feed and Mystro offer history — raw, unstructured
video showing individual trips with fare, miles, minutes, and disposition

### Process
