---
name: /forge-infra-scale
description: Vertical and horizontal scaling strategy for high-performance clusters.
category: Operations
status: Stable
methodology: Caesar Nexus Logic
---

# Infrastructure Scaling (/forge-infra-scale)

## Caesar Nexus Execution Logic

### Phase 1: Load Analysis
- **Call**: `/forge-monitor`
- **Action**: Analyze traffic patterns and identify resource exhaustion points.

### Phase 2: Scaling Strategy
- **Call**: `/forge-plan`
- **Action**: Orchestrate Autoscale rules and database read-replica expansions.

### Phase 3: Execution (Scaling)
- **Implement**: Apply resource limit updates or instance count adjustments.

### Phase 4: Performance Validation
- **Call**: `/forge-test`
- **Action**: Stress test the newly scaled environment.

### Phase 5: Recording & Tuning
- **Update**: Scaling logs and tune autoscale thresholds.

## Iron Laws
- **Cost Awareness**: Always evaluate cost implications before scaling out.
- **Predictive Scaling**: Prioritize schedule-based scaling for known traffic peaks.
- **Zero Downtime Scaling**: Ensure scaling events do not impact end-user latency.

