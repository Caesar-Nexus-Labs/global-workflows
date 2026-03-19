---
name: /nexus-validate-eng
description: Engineering quality gate ensuring code adherence and architectural integrity.
category: Compliance & Audit
status: Stable
methodology: Nexus Protocol
---

# Engineering Validation (/nexus-validate-eng)

## Caesar Nexus Execution Logic

### Phase 1: Code Ingestion
- **Action**: Gather target files and documentation via `/forge-scout`.

### Phase 2: Logic & TDD Audit
- **Call**: `/forge-test`
- **Action**: Verify 100% test pass rate and coverage requirements.

### Phase 3: Architectural Adherence
- **Action**: Check against `forge-development-rules.md` and `C4/LikeC4` blueprints.
- **Verify**: Zero circular dependencies and clean-code compliance.

### Phase 4: Security & Performance
- **Action**: Scan for secrets, vulnerabilities, and performance bottlenecks.
- **Gate**: Score ≥ 9.5 required.

### Phase 5: Verdict & Handoff
- **Action**: Approve or trigger `/nexus-remediate`.
- **Update**: Project health status.

## Iron Laws
- **Plan Sync**: Code must match the approved `/forge-plan` 1:1.
- **Zero Orphan**: All new files must belong to a defined module.
- **Clean Registry**: No legacy or commented-out code permitted.

