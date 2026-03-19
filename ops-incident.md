---
name: /ops-incident
description: On-call orchestration and forensic post-mortem leader.
category: DevOps
status: Stable
methodology: Caesar Nexus Logic
---

# Incident Command (/ops-incident)

## 1. Description
A high-fidelity framework for triage, resolution, and forensic investigation of system outages or security breaches.

## 2. Caesar Nexus Execution Loop

### Phase 1: Triage & Paging
- Immediate assessment of severity (SEV1-4) and automated paging via `/ops-page`.
- Activation of the war room and role assignment (Command, Ops, Comms).

### Phase 2: Mitigation (Stop the Bleed)
- Rapid state restoration using `/checkpoint-restore` if applicable.
- Traffic shifting via `/ops-canary` to bypass faulty regions.

### Phase 3: Root Cause Analysis (RCA)
- Deep log inspection across the telemetry stack.
- Identification of the "First Domino" and the failure chain.

### Phase 4: Remediation
- Implementation of a long-term fix using the `/forge-cook` loop.
- Verification through 100% test pass in a mirrored environment.

### Phase 5: Post-Mortem
- Mandatory forensic documentation in the technical journal.
- Update of runbooks to prevent recurrence.

## 3. Iron Laws
- **Blameless Culture**: Focus on system failure, not human error.
- **Truth First**: No public communication before state verification.
- **MTTR Priority**: Every action must prioritize reducing the Mean Time To Repair.

