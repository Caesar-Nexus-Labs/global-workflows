---
name: trigger-market-data-audit
description: Real-time data integrity verification for marketing pipelines.
event: trigger-pre-tool
methodology: Caesar Nexus Logic
---

# Trigger: Marketing Data Audit (`trigger-market-data-audit`)

## 1. Description
Automatically ensures data high-fidelity before any analytics or forecasting operation begins. It acts as a deterministic guard for the "Data Layer".

## 2. Trigger Logic
- **Invoke Event**: `trigger-pre-tool`.
- **Matchers**: `/market-data-analytics`, `/market-data-mmm`, `/market-data-revenue`.
- **Action**:
    - Run a 1-second "Freshness & Null-Check" scan.
    - Verify schema mapping against `marketing-data-schema.json`.
- **Block Condition**: If data quality score is < 95%, block execution and demand `/market-data-audit` execution first.

## 3. Strategic Alignment
- **Goal**: "Garbage In, Garbage Out" prevention.
- **Speed**: Must complete in < 500ms to avoid disrupting the analyst workflow.
