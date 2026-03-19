---
name: /market-analytics
description: Data-driven performance tracking and strategic ROI analysis.
category: Marketing & Growth
status: Stable
methodology: Caesar Nexus Logic
---

# Marketing Analytics Workflow (/market-analytics)

## Caesar Nexus Execution Logic

### Phase 1: Data Collection & Cleaning
- **Call**: `/market-data-audit` and `/market-cdp-sync` to ensure high-fidelity raw data and identity resolution.
- **Action**: Aggregate data from GA4, CRM, and Ad platforms.
- **Verify**: Data accuracy and remove outliers/PII.

### Phase 2: Performance Review
- **Action**: Identify trends and compare vs. quarterly goals.
- **Action**: Benchmark period-over-period performance (WoW, MoM).

### Phase 3: Visualization
- **Call**: `/market-dashboard`
- **Action**: Update dashboards with real-time attribution data.

### Phase 4: Verification & Insights
- **Agent**: `data-scientist`, `LTV Strategist`, and `MMM Scientist` audit.
- **Call**: `/market-ltv-model` and `/market-mmm-forecast` for predictive forecasting and budget elasticity.
- **Action**: Extract "The Why" behind the numbers (Attribution modeling).

### Phase 5: Strategy Update
- **Call**: `/market-plan`
- **Action**: Document learnings and feed recommendations into business strategy.

## Iron Laws
- **Single Source of Truth**: All reports must pull from the verified Caesar Nexus Data Lake.
- **Actionable Only**: No "Vanity Metrics"; focus on CAC, LTV, and ROI.
- **Privacy Gated**: Zero exposure of sensitive customer data in reporting.

