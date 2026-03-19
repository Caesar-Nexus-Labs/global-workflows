---
name: /ops-canary
description: Progressive rollout and traffic distribution specialist.
category: DevOps
status: Stable
methodology: Caesar Nexus Logic
---

# Canary Deployment Strategy (/ops-canary)

## 1. Description
Safely introduces new features to production by routing a small percentage of traffic to the new version before a full rollout.

## 2. Execution Logic
1. **Baseline Lock**: Capture current error rate and latency metrics as the comparative baseline.
2. **vNext Deployment**: Deploy the new version with zero initial traffic.
3. **Phase 1 (5%)**: Route 5% of traffic to vNext and monitor for 5 minutes (Golden Signals audit).
4. **Phase 2 (25%)**: If stable, increase to 25% and monitor for another 10 minutes.
5. **Full Cutover**: Scale to 100% and decommission the legacy cluster.
6. **Automatic Abort**: Immediate rollback if error rates exceed baseline by > 2%.

## 3. Iron Laws
- **Continuous Audit**: Automated comparisons between Version A and Version B are mandatory.
- **Manual Halt**: The architect can pause the rollout at any stage via `/ops-status`.
- **Stateless Bias**: Canary is only used for services with externalized state (Redis/Postgres).

