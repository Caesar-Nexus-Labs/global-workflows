---
name: /nexus-validate-infra
description: Infrastructure and operations compliance gate ensuring security and scalability.
category: Compliance & Audit
status: Stable
methodology: Nexus Protocol
---

# Infrastructure Validation (/nexus-validate-infra)

## Caesar Nexus Execution Logic

### Phase 1: IaC Audit
- **Action**: Scan Terraform/CloudFormation files for configuration errors.
- **Goal**: Verify against security best practices (CIS Benchmarks).

### Phase 2: Security & Network Check
- **Action**: Verify firewalls, security groups, and encryption protocols.
- **Verify**: Secrets isolation and IAM least-privilege compliance.

### Phase 3: Scalability & Redundancy
- **Action**: Audit Autoscale rules and multi-AZ configurations.
- **Verify**: Disaster recovery and rollback readiness.

### Phase 4: Provisioning Dry Run
- **Call**: `/forge-test`
- **Action**: (Optional) Sandbox deployment and health-check verification.

### Phase 5: Verdict & Handoff
- **Action**: Approve for production deploy or trigger `/nexus-remediate`.
- **Log**: Save audit report.

## Iron Laws
- **Immutable Infrastructure**: Manual cloud changes are strictly forbidden.
- **Security-First**: Any unencrypted sensitive data halts the process.
- **Cost Awareness**: Verify resource tags and budget limits.

