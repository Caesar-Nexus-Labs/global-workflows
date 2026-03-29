# /ops-deploy

> **Official Deployment Conductor** — Comprehensive orchestration of infrastructure, CI/CD, secrets, and progressive rollout.

## Command Metadata

| Field | Value |
|-------|-------|
| **Slug** | `/ops-deploy` |
| **Kit** | DevOps (`/ops-*`) |
| **Type** | Orchestrator (main entry point) |
| **Conductor Persona** | Caesar Ops Manager |
| **Supporting Collaborators** | Infrastructure Architect, Deployment Validator |
| **Prerequisites** | `/nexus-validate-infra` MUST pass |
| **Triggers** | `trigger-prompt-submit`, `trigger-post-tool`, `trigger-session-end` |
| **Estimated Duration** | 15-30 minutes (depending on infrastructure size) |

---

## Description

`/ops-deploy` orchestrates the **complete deployment pipeline** from infrastructure planning through production validation. It is the primary entry point for all deployment workflows and executes the following steps in strict sequence:

1. **Infrastructure Blueprint** (`/ops-infra-plan`) → Generate Terraform/IaC templates
2. **CI/CD Pipeline** (`/ops-setup-cicd`) → Build automated deployment pipeline
3. **Secrets Management** (`/ops-secrets`) → Configure vaults and credential handling
4. **Infrastructure Apply** (`/ops-terraform`) → Apply IaC changes (idempotent)
5. **Container Orchestration** (`/ops-k8s`) → Setup Kubernetes/container runtime
6. **Deployment Validation** (`/ops-validate-deploy`) → Run smoke tests and health checks
7. **Progressive Rollout** (`/ops-canary`) → Implement staged rollout strategy
8. **Observability Setup** (`/ops-monitoring`) → Configure telemetry and alerting

Each step must succeed before proceeding to the next. Any failure triggers automatic rollback.

---

## Skill Routing

- **Agent ID**: `agent.ops_manager`
- **Process Hub**: `cn:c15_plan`
- **Primary Workflow Bundle**: `cn:c70_cloud_devops`
- **Supporting Workflows**:
  - `cn:c60_terraform_infrastructure`
  - `cn:c70_kubernetes_deployment`
  - `cn:c70_deployment_validation_config_validate`

---

## Parameters

### Required Flags

| Flag | Type | Description |
|------|------|-------------|
| `--environment` | string | Target environment: `dev`, `staging`, `prod` |
| `--version` | string | Application version to deploy (e.g., `1.2.3`) |
| `--dry-run` | boolean | Plan changes without applying (default: `false`) |

### Optional Flags

| Flag | Type | Default | Description |
|------|------|---------|-------------|
| `--skip-tests` | boolean | `false` | Skip `/ops-validate-deploy` smoke tests (not recommended) |
| `--rollback-on-failure` | boolean | `true` | Auto-rollback if any step fails |
| `--parallel-ops` | boolean | `false` | Run k8s & monitoring setup in parallel |
| `--notify-slack` | string | `null` | Slack channel for notifications |
| `--max-retries` | integer | `3` | Max retry attempts per step |

---

## Execution Logic

### Pre-Flight Checks

1. Verify `/nexus-validate-infra` passed → If failed: ABORT
2. Validate deployment parameters → If invalid: ABORT
3. Check infrastructure state → If unhealthy: DEFER to `/ops-incident`

### Main Pipeline (8 Steps in Sequence)

**STEP 1**: `/ops-infra-plan` → Generate Terraform plan (on failure: ABORT)
**STEP 2**: `/ops-setup-cicd` → Build CI/CD pipeline (on failure: ABORT)
**STEP 3**: `/ops-secrets` → Configure secrets vault (on failure: ABORT)
**STEP 4**: `/ops-terraform` → Apply infrastructure (on failure: ROLLBACK)
**STEP 5**: `/ops-k8s` → Deploy to Kubernetes (on failure: ROLLBACK)
**STEP 6**: `/ops-validate-deploy` → Run smoke tests (on failure: ALERT/ROLLBACK)
**STEP 7**: `/ops-canary` → Progressive rollout (on failure: PAUSE)
**STEP 8**: `/ops-monitoring` → Setup observability (on failure: WARN)

### Rollback Strategy

- Checkpoint state before `/ops-terraform`
- On failure: restore from checkpoint + undo kubectl deployments
- Max rollback time: 5 minutes
- Log all actions for audit trail

---

## Output Format

```json
{
  "deployment_id": "deploy-20260317-145632",
  "environment": "prod",
  "version": "1.2.3",
  "status": "success|partial|failed",
  "total_duration_ms": 28400,
  "steps_completed": 8,
  "resources_deployed": 42,
  "pods_running": 24,
  "errors": []
}
```

---

## Security

- ✅ Requires `/nexus-validate-infra` gate
- ✅ Secrets never logged (stripped by trigger-post-tool)
- ✅ All actions audited via trigger-post-tool
- ✅ Rollback history kept for compliance

---

**Status**: PROD-READY ✅
**Last Updated**: 2026-03-17
**Version**: 1.0.0
