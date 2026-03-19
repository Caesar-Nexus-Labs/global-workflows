---
name: /market-data-audit
description: Marketing data quality and pipeline audit to ensure high-fidelity insights.
category: Marketing & Growth
status: Stable
methodology: Caesar Nexus Logic
---

# Marketing Data Audit (/market-data-audit)

## 1. Description
Enforces high-fidelity data integrity across the marketing stack. It ensures that every decision made by the Caesar Nexus Marketing Engine is built on a foundation of clean, verified, and structured data.

## 2. Caesar Nexus Execution Loop

### Phase 1: Pipeline Scout
- **Action**: Audit data ingestion points (Pixel, API, CRM).
- **Check**: Verify data freshness and latency (< 5 mins).

### Phase 2: Schema Validation
- **Action**: Validate incoming event schemas against the `Caesar-Nexus-Data-Dictionary`.
- **Identify**: Mismatched properties, missing UTMs, or duplicate events.

### Phase 3: PII & Compliance Scrub
- **Action**: Run the `/nexus-audit` logic for privacy.
- **Verify**: Ensure zero PII leakage into analytics platforms.

### Phase 4: Data Quality Scoring
- **Action**: Generate a Data Integrity Score (Target: ≥ 98%).
- **Call**: `/market-analytics` to reset baselines if integrity is low.

### Phase 5: Handoff to Analytics
- **Action**: Finalize the clean dataset for ROI modeling.
- **Update**: Data lineage documentation.

## 3. Iron Laws
- **Quality Gate**: No marketing campaign execution without a verified `/market-data-audit` pass.
- **Accuracy First**: If data integrity is < 95%, all automated decisions are paused.
- **Zero Orphan Events**: Every tracking event must map to a defined business KPI.
