# /market-campaign

> **Full-Cycle Campaign Orchestration** — End-to-end campaign planning, execution, and optimization.

## Metadata

- **Slug**: /market-campaign
- **Type**: Campaign Management
- **Agents**: Campaign Manager, Creative Director, Analytics Manager
- **Calls**: /market-funnel, /market-write, /market-content

## Description

Orchestrates complete campaign lifecycle from planning through measurement:
- Campaign brief & objectives
- Target audience definition
- Creative & messaging strategy
- Channel mix & sequencing
- Budget distribution
- Performance tracking
- Optimization & iterations

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --campaign-name | string | Campaign identifier |
| --campaign-type | string | product-launch, seasonal, awareness, conversion |
| --target-audience | string | Segment description |
| --duration | duration | Campaign run length |
| --budget | integer | Campaign budget |

## Output

```json
{
  "campaign_id": "camp-spring-2026",
  "status": "active",
  "channels": 4,
  "impressions": 2500000,
  "clicks": 45000,
  "conversions": 1500,
  "ctr": "1.8%",
  "conversion_rate": "3.3%"
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
