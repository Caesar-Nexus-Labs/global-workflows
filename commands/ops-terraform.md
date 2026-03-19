# /ops-terraform

> **Infrastructure Application** — Apply IaC changes (idempotent).

## Metadata

- **Slug**: /ops-terraform
- **Type**: Infrastructure Apply
- **Agents**: Infrastructure Engineer, DevOps Engineer

## Description

Applies Terraform changes from /ops-infra-plan. Idempotent and safe to retry. Checkpoints state for rollback capability.

## Parameters

| Flag | Type | Default | Description |
|------|------|---------|-------------|
| --plan-file | string | required | Terraform plan file |
| --auto-approve | boolean | false | Skip manual approval |
| --lock-timeout | duration | 5m | State lock timeout |

## Output

```json
{
  "apply_id": "apply-20260317-145632",
  "status": "success",
  "resources_created": 42,
  "resources_modified": 3,
  "duration_ms": 45000,
  "state_checkpoint": "checkpoint-v1"
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
