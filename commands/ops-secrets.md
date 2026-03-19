# /ops-secrets

> **Secrets Management** — Configure vaults and manage credentials securely.

## Metadata

- **Slug**: /ops-secrets
- **Type**: Security Management
- **Agents**: Security Engineer, DevOps Engineer

## Description

Configures a secrets manager (e.g., AWS Secrets Manager) or equivalent for secure credential storage and rotation. Integrates with K8s for secret injection.

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --vault-type | string | vault, aws-secrets, gcp-secret-manager |
| --secret-names | array | Secret identifiers to configure |
| --rotation-policy | string | Secret rotation frequency |

## Output

```json
{
  "vault_id": "vault-20260317-145632",
  "vault_type": "aws-secrets",
  "secrets_configured": 12,
  "rotation_enabled": true,
  "k8s_secret_sync": "active"
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
