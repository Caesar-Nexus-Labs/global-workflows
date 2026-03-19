---
name: /forge-maintenance
description: Stability, security, and gradual modernization for long-running projects.
category: Operations & Lifecycle
status: Stable
methodology: Caesar Nexus Logic
---

# Maintenance & Legacy Support (/forge-maintenance)

## Caesar Nexus Execution Logic

### Phase 1: Health Audit
- **Call**: `/forge-scout --deep`
- **Action**: Identify technical debt, security gaps, and outdated crates.

### Phase 2: Planning & Prioritization
- **Call**: `/forge-plan`
- **Action**: Generate roadmap for modernization and bug backlog.

### Phase 3: Execution (Patching & Upgrades)
- **Call**: `/forge-cook`
- **Action**: Batch updates for dependencies and security patches.

### Phase 4: Verification (Regression)
- **Call**: `/forge-test`
- **Action**: Run full suite to ensure 0 breakage during maintenance.

### Phase 5: Reporting & Finalization
- **Update**: `CHANGELOG.md` and project health logs.

## Iron Laws
- **Safety First**: Never compromise product availability.
- **Gradual Change**: Prioritize incremental improvements over "Big Bang".
- **Legacy Persistence**: Respect constraints until refactor is approved.

