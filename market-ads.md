# /market-ads

> **Integrated Ad Campaign Management** — Create, launch, and optimize ads across all major platforms.

## Metadata

- **Slug**: /market-ads
- **Type**: Performance Marketing
- **Agents**: Paid Ads Manager, Performance Specialist

## Description

Manages end-to-end ad campaigns:
- Audience targeting & segmentation
- Creative variations & A/B testing
- Budget allocation & bid strategies
- Multi-platform coordination (Google, Facebook, LinkedIn, TikTok, Twitter)
- Performance tracking & optimization
- ROAS & efficiency metrics

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --platforms | array | google, facebook, linkedin, tiktok, twitter |
| --budget | integer | Total ad spend |
| --target-cpa | integer | Cost per acquisition goal |
| --duration | duration | Campaign run length |

## Output

```json
{
  "campaign_id": "ads-spring-2026",
  "platforms": 4,
  "impressions": 5000000,
  "clicks": 125000,
  "conversions": 4200,
  "cpc": 1.50,
  "cpa": 17.86,
  "roas": 3.8
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
