# /market-plan

> **Strategic Quarterly Planning** — Comprehensive go-to-market strategy and campaign roadmap.

## Metadata

- **Slug**: /market-plan
- **Type**: Strategy
- **Conductor Persona**: Growth Product Lead
- **Supporting Collaborators**: Product Marketer, Growth Hacker
- **Duration**: 4-8 hours
- **Output**: Quarterly marketing strategy document

## Description

Develops comprehensive quarterly marketing strategy including:
- Market analysis & positioning
- Campaign calendar & sequencing
- Budget allocation across channels
- KPI targets & success metrics
- Competitive positioning
- Growth initiatives & experiments
- Team allocation & dependencies

## Skill Routing

- **Agent ID**: `agent.growth_product_lead`
- **Process Hub**: `cn:c15_plan`
- **Primary Workflow**: `cn:c70_product_manager`
- **Supporting Workflow**: `cn:c70_marketing_ideas`

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --quarter | string | Q1 2026, Q2 2026, etc |
| --market-research | file | Latest market data |
| --budget-total | integer | Total quarterly budget |
| --growth-target | integer | Revenue or user growth target |

## Output

```json
{
  "plan_id": "plan-q1-2026",
  "quarter": "Q1 2026",
  "revenue_target": 500000,
  "campaigns": 6,
  "budget_allocated": 75000,
  "kpis": {
    "customer_acquisition": 150,
    "conversion_rate": "3.5%",
    "cac": 500
  }
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
