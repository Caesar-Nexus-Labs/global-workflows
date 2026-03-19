---
name: /nexus-remediate
description: Structured recovery and remediation of compliance or security failures.
category: Compliance & Audit
status: Stable
methodology: Nexus Protocol
---

# Systematic Remediation (/nexus-remediate)

## Caesar Nexus Execution Logic

### Phase 1: Failure Analysis
- **Action**: Analyze the validation/audit failure report.
- **Goal**: Identify root cause and impact radius.

### Phase 2: Remediation Plan
- **Call**: `/forge-plan`
- **Action**: Orchestrate "Fix-it" tasks (Code, Content, or Infra).

### Phase 3: Execution (Recovery)
- **Call**: `/forge-cook`
- **Action**: Implement fixes using the TDD Green-Refactor cycle.

### Phase 4: Verification (Re-Audit)
- **Call**: `/nexus-validate-*`
- **Action**: Mandatory validation pass of repaired artifacts.

### Phase 5: Closure & Reporting
- **Action**: Update the risk registry via `/nexus-risk`.
- **Log**: Resolution report to `reports/nexus-remediation-*.md`.

## Iron Laws
- **Time Gated**: High-risk failures must be remediated within 2 hours.
- **No Recurring Errors**: Implement guards to prevent failure repetition.
- **Full Transparency**: All remediation steps must be documented and auditable.

