# /ops-infra-plan

> **Infrastructure Blueprinting** — Generate Terraform/IaC templates.

## Metadata

- **Slug**: /ops-infra-plan
- **Type**: Planning
- **Agents**: Infrastructure Architect, Cloud Engineer

## Description

Generates Terraform plan based on architecture definitions. Outputs resource diff showing creates, modifies, destroys.

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --environment | string | dev, staging, prod |
| --cloud-provider | string | aws, gcp, azure |
| --region | string | e.g. us-east-1 |
| --config-file | string | infrastructure config YAML |

## Output

```json
{
  "plan_id": "plan-20260317-145632",
  "environment": "prod",
  "resources_to_create": 42,
  "resources_to_modify": 3,
  "terraform_plan_file": "terraform_prod.plan"
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
