# /market-funnel

> **Customer Journey Design** — Map awareness → consideration → conversion → retention paths.

## Metadata

- **Slug**: /market-funnel
- **Type**: Growth Mechanics
- **Agents**: Growth Strategist, Data Analyst

## Description

Designs customer journey funnels with:
- Awareness stage optimization
- Consideration content & touchpoints
- Conversion optimization
- Retention mechanics & upsell
- Drop-off analysis & recovery flows
- Lifecycle value predictions

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --product-type | string | B2B SaaS, e-commerce, marketplace, etc |
| --target-segment | string | Audience segment |
| --target-acq-cost | integer | Target customer acquisition cost |

## Output

```json
{
  "funnel_id": "funnel-2026",
  "awareness_rate": "100%",
  "consideration_rate": "8%",
  "conversion_rate": "3.3%",
  "retention_rate": "85%",
  "ltv_predicted": 15000
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
