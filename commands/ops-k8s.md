# /ops-k8s

> **Kubernetes Orchestration** — Deploy and configure Kubernetes workloads.

## Metadata

- **Slug**: /ops-k8s
- **Type**: Container Orchestration
- **Agents**: Kubernetes Engineer, Platform Engineer

## Description

Manages K8s cluster setup, namespace creation, deployments, RBAC, network policies, and service configuration. Idempotent.

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --manifest-file | string | K8s manifest YAML |
| --namespace | string | K8s namespace (default: default) |
| --replicas | integer | Desired replica count |
| --image | string | Container image & tag |

## Output

```json
{
  "deployment_id": "k8s-20260317-145632",
  "namespace": "production",
  "pods_running": 24,
  "replicas_desired": 24,
  "service_endpoints": ["api.prod.internal:8080"],
  "status": "ready"
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
