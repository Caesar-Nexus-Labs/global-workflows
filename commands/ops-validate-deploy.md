# /ops-validate-deploy

> **Deployment Validation Gate** — Health checks and smoke tests before traffic.

## Metadata

- **Slug**: /ops-validate-deploy
- **Type**: Quality Gate (CRITICAL)
- **Agents**: QA Engineer, Release Manager
- **SLA**: < 5 minutes

## Description

Runs comprehensive health checks, HTTP endpoint validation, database connectivity tests, and API response verification. MUST pass before /ops-canary begins.

## Parameters

| Flag | Type | Default | Description |
|------|------|---------|-------------|
| --deployment-id | string | required | ID from /ops-deploy |
| --health-endpoints | array | /health, /ready | URLs to probe |
| --timeout | integer | 300 | Max seconds to wait |
| --strict-mode | boolean | true | Fail on ANY warning |
| --retry-count | integer | 5 | Probe retries |

## Validation Tests

- HTTP endpoints return 200 OK
- Database connection & migrations OK
- API response schema validation
- Pod replica count = desired
- TLS certificates valid (> 30 days)
- No security warnings

## Output

```json
{
  "validation_id": "val-20260317-145632",
  "status": "passed",
  "tests_run": 42,
  "tests_passed": 42,
  "pods_running": 24,
  "endpoints_healthy": true
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
