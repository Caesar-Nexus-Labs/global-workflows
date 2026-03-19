---
name: /forge-optimize
description: Data-driven refinement of system speed and efficiency.
category: Code Quality
status: Stable
methodology: Caesar Nexus Logic
---

# Performance Optimization (/forge-optimize)

## Caesar Nexus Execution Logic

### Phase 1: Detection & Baselines
- **Action**: Identify bottlenecks using profilers/APM.
- **Store**: Baseline KPIs (Latency, VRAM).

### Phase 2: Optimization Strategy
- **Call**: `/forge-plan --auto`
- **Action**: Map strategy (Tuning, Refinement, Caching).

### Phase 3: Execution (Tuning)
- **Implement**: Database indexing, Redis caching, removal of redundant allocations.

### Phase 4: Benchmarking
- **Call**: `/forge-test`
- **Compare**: Baseline vs. New KPIs.

### Phase 5: Finalization
- **Verify**: Zero functional regression.
- **Update**: Documentation of performance gains.

## Iron Laws
- **Measure First**: Never optimize without a verified baseline.
- **No Premature Optimization**: Focus on verified bottlenecks.
- **Stability-First**: Efficiency must not compromise system stability.

