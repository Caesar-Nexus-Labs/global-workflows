---
name: trigger-market-analytics-gate
description: Data integrity verification before marketing performance analysis.
event: trigger-pre-tool
matcher: "/market-data-analytics"
---

# Trigger: Marketing Analytics Gate (`trigger-market-analytics-gate`)

## 1. Description
Ensures that all marketing data is clean, synchronized, and follows the required schema before any ROI or performance calculation. It prevents "Dirty Data" from polluting strategic decisions.

## 2. Execution Logic
- **Invoke Event**: `trigger-pre-tool`.
- **Action**:
    1. Scan the active data source for `NULL` values or schema mismatches.
    2. Check the "Data Freshness" timestamp. If > 24h old, trigger `/market-data-cdp` sync.
    3. Verify internal attribution weights are loaded.
- **Guard**: If the data audit score is < 98%, block the analysis and force a `/market-data-audit` run.

## 3. Iron Laws
- **High-Fidelity**: Strategy is only as good as its data. Never allow an analysis on unverified data.
- **Speed**: Non-blocking verification (must complete in < 500ms).
