# /market-onboarding

> **First-7-Days User Success** — Onboarding sequences and retention mechanics for new customers.

## Metadata

- **Slug**: /market-onboarding
- **Type**: Retention & Lifecycle
- **Agents**: Lifecycle Manager, Customer Success Lead

## Description

Designs and optimizes first-7-days onboarding:
- Activation tasks & success criteria
- Email welcome sequence
- In-app guidance & tooltips
- Aha-moment identification
- Usage milestones & celebrations
- Win-back mechanics for at-risk users
- Referral loop integration

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --product-type | string | SaaS, e-commerce, creator-platform |
| --target-aha-day | integer | Day user should experience aha-moment |
| --retention-target | integer | Day 7 retention % target |

## Output

```json
{
  "onboarding_id": "onb-2026",
  "emails_in_sequence": 5,
  "in_app_touchpoints": 8,
  "day_1_engagement": "72%",
  "day_7_retention": "64%",
  "aha_conversion": "58%"
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
