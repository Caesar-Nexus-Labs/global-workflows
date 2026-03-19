---
name: "forge:canary"
description: "Incremental rollout of new features with automatic rollback on error."
category: "c36_devops"
status: "verified"
methodology: "methodology"
---

# Canary Deployment (/forge-canary)

## 5-Stage Caesar Nexus Logic

### Phase 1: Target Definition
- Define traffic percentages (5% -> 25% -> 50% -> 100%).

### Phase 2: Configuration
- Setup Load Balancer or Service Mesh rules for traffic split.

### Phase 3: Initial Rollout (5%)
- **Action**: Deploy to a small subset of users.

### Phase 4: Monitoring Phase
- **Rule**: If error rate > 1% or latency > 200ms, AUTO-ROLLBACK.

### Phase 5: Full Rollout
- Gradually increase traffic until 100% is reached.

