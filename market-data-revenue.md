---
name: /market-revenue-forecast
description: Time-series revenue and churn prediction to optimize growth forecasting.
category: Marketing & Growth
status: Stable
methodology: Caesar Nexus Logic
---

# Revenue & Churn Forecasting (/market-revenue-forecast)

## 1. Description
Uses historical sales data and product usage signals to predict future revenue streams. It identifies potential churn before it happens and forecasts quarterly expansion opportunities.

## 2. Caesar Nexus Execution Loop

### Phase 1: Historical Baseline (Scout)
- **Action**: Extract 24+ months of MRR/ARR data.
- **Check**: Segment by product line and customer tier.

### Phase 2: Signal Extraction (Blueprint)
- **Action**: Correlate revenue with marketing spend (`/market-mmm-forecast`) and product usage (`/market-product-growth`).
- **Identify**: Key leading indicators of churn (e.g., login inactivity).

### Phase 3: Time-Series Modeling (Cook)
- **Agent**: `Revenue Forecaster` execution.
- **Method**: ARIMA or Prophet models to forecast revenue with confidence intervals.

### Phase 4: Churn & Pipeline Audit (Gate)
- **Action**: Identify "At-Risk" revenue segments.
- **Verify**: Calculate Net Revenue Retention (NRR) and Gross Revenue Retention (GRR).

### Phase 5: Handoff to Finance/Strategy (Watch)
- **Action**: Export forecast reports to the Marketing Master Dashboard.
- **Call**: `/market-plan` to adjust growth targets based on forecast.

## 3. Iron Laws
- **Conservative Bias**: Forecasts must always include a "Worst-Case" and "Expected" scenario.
- **Multi-Signal**: Never forecast based on spend alone; always include product usage signals.
- **Zero Lag**: Revenue data must be updated and re-forecasted every 24 hours.
