---
name: /nexus-audit
description: Formal audit of system state, security, and process adherence.
category: Compliance & Audit
status: Stable
methodology: Nexus Protocol
---

# Systematic Governance Audit (/nexus-audit)

# Systematic Governance Audit (/nexus-audit)

## 1. Description
The supreme governance layer. It performs formal validation of system state, security, brand integrity, and process adherence across the Caesar Nexus ecosystem.

## 2. Caesar Nexus Execution Loop

### Phase 1: Scope & Risk Triage
1. **Domain Isolation**: Define audit area (Engineering kit vs Marketing kit vs Infra).
2. **Vulnerability Map**: Invoke **[/nexus-risk](./nexus-risk.md)** to identify critical control points.
3. **Trigger**: `trigger-rules-reminder` syncs the current audit with `AGENT_CORE_PROTOCOL.md`.

### Phase 2: Evidence Aggregation (Truth Collection)
1. **Technical Data**: Trigger **[/nexus-report](./nexus-report.md)** for logs, commits, and test outputs.
2. **Logic Check**: Invoke **[/nexus-validate-eng](./nexus-validate-eng.md)** for architectural compliance.
3. **Brand Audit**: (If marketing) Invoke **[/nexus-validate-market](./nexus-validate-market.md)**.

### Phase 3: Verification & Integrity Check
1. **Fact-Checking**: Cross-verify evidence against the Master Index and Git Hash.
2. **Paradox Detection**: Use **[/forge-problem-solving](./forge-problem-solving.md)** for high-complexity policy conflicts.
3. **Metric Calculation**: Calculate the current Integrity Score (0-100%).

### Phase 4: Remediation & Correction
1. **Failure Correction**: Trigger **[/nexus-remediate](./nexus-remediate.md)** for any failed audit points.
2. **Security Lock**: Redirect to **[/ops-audit-infra](./ops-audit-infra.md)** for infra-level hardening.

### Phase 5: Verdict & Archival
1. **Formal Report**: Generate the final Phase Integrity Report in `integrity_ledger/`.
2. **Governance Sync**: Trigger `trigger-task-logger` to record the verdict in the Master Hub.

## 3. Iron Laws
- **Empirical Proof Mandatory**: No audit claim shall be accepted without a linked binary or documented evidence file.
- **Zero Omission Policy**: Every identified minor risk must be logged and remediation trackable.
- **Auditor Autonomy**: The audit agent must have no prior participation in the phase's implementation.

