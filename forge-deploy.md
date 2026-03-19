---
name: /forge-deploy
description: Continuous integration and high-availability deployment cycles.
category: Operations
status: Stable
methodology: Caesar Nexus Logic
---

# Systematic Deployment (/forge-deploy)

## Caesar Nexus Execution Logic

### Phase 1: Build & Artifacts
- **Action**: Compile project with extreme Rust parallelism and build optimized containers.

### Phase 2: Deployment Planning
- **Call**: `/forge-plan`
- **Action**: Orchestrate Rolling Update or Blue/Green deployment strategy.

### Phase 3: Execution (Delivery)
- **Implement**: Push artifacts to staging or production clusters.

### Phase 4: Verification (Smoke Test)
- **Call**: `/forge-test`
- **Action**: Automated verification of critical health endpoints.

### Phase 5: Monitoring & Monitoring
- **Call**: `/forge-monitor`
- **Action**: Verify system stability and log baseline performance.

## Iron Laws
- **Test Gate**: Never deploy if the test suite is not 100% green.
- **Canary Release**: Prefer gradual rollouts for major production changes.
- **Rollback Readiness**: Deploy only if a verified rollback plan exists.

