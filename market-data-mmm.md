---
name: /market-mmm-forecast
description: Marketing Mix Modeling (MMM) for budget optimization and channel elasticity.
category: Marketing & Growth
status: Stable
methodology: Caesar Nexus Logic
---

# Marketing Mix Modeling (/market-mmm-forecast)

## 1. Description
A top-down statistical model that measures the effectiveness of every marketing dollar spent. It accounts for external factors (seasonality, economic trends) and internal channel performance to optimize the budget mix.

## 2. Caesar Nexus Execution Loop

### Phase 1: Historical Data Ingestion (Scout)
- **Invoke**: `/market-data-audit` to gather 2+ years of spend and revenue data.
- **Action**: Aggregate offline and online spend data (Ad platforms, TV, Print, Email).

### Phase 2: Feature Engineering (Blueprint)
- **Action**: Map external variables (holidays, competitor activity).
- **Control**: Apply "Adstock" effects (carryover effect of ads over time).

### Phase 3: Model Training (Cook)
- **Agent**: `MMM Scientist` execution.
- **Method**: Bayesian regression or Ridge regression to calculate channel coefficients.

### Phase 4: Elasticity & Optimization (Gate)
- **Action**: Run "Budget Elasticity" simulations.
- **Verify**: Calculate Marginal ROI (mROI) for each channel.

### Phase 5: Strategic Forecast (Watch)
- **Action**: Generate the "Optimal Spend Mix" for the next quarter.
- **Call**: `/market-plan` to update budget allocation.

## 3. Iron Laws
- **Top-Down Mastery**: MMM must be used alongside bottom-up attribution to eliminate bias.
- **External Awareness**: Never ignore external factors (market trends) in the model.
- **Evidence-First**: All spend shifts must be backed by a ≥ 90% confidence interval.
