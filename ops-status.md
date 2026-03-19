# /ops-status

> **Infrastructure Health Dashboard** — Real-time monitoring and status reporting.

## Metadata

- **Slug**: /ops-status
- **Type**: Monitoring Dashboard
- **Agents**: Reliability Engineer, DevOps Engineer

## Description

Real-time view of infrastructure health including pod status, resource utilization, database replication lag, network throughput, error rates, and recent alerts.

## Parameters

| Flag | Type | Default | Description |
|------|------|---------|-------------|
| --environment | string | required | dev, staging, prod |
| --format | string | table | json, table, html |
| --refresh | boolean | false | Continuous polling |

## Output

```json
{
  "status_id": "status-20260317-145632",
  "overall_health": "healthy",
  "pods_running": 24,
  "pods_failed": 0,
  "cpu_usage": "62%",
  "memory_usage": "78%",
  "error_rate": "0.02%",
  "last_deployment": "20260317-145632"
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
