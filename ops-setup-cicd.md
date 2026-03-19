# /ops-setup-cicd

> **CI/CD Pipeline Orchestration** — Build automated deployment pipelines.

## Metadata

- **Slug**: /ops-setup-cicd
- **Type**: Pipeline Setup
- **Agents**: DevOps Engineer, Automation Specialist

## Description

Creates CI/CD pipelines (GitHub Actions, GitLab CI, Jenkins) for automated build, test, and deployment workflows.

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --ci-platform | string | github-actions, gitlab-ci, jenkins |
| --repository | string | Repository URL |
| --build-config | file | .yml config for build steps |
| --deploy-config | file | .yml config for deployment |

## Output

```json
{
  "pipeline_id": "pipe-20260317-145632",
  "platform": "github-actions",
  "status": "created",
  "webhook_url": "https://github.com/webhooks/..."
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
