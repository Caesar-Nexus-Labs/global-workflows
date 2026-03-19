---
description: Bootstrap a new project or implement major feature from zero with full orchestration.
---

# Project Bootstrap (/forge-bootstrap)

## 1. Description

The "Genesis Command". Orchestrates the birth of a new project or major feature from zero, ensuring the foundation is structurally sound and follows Caesar Nexus standards.

## 2. Caesar Nexus Execution Loop

### Phase 1: Genesis & Blueprinting

1. **Initial Elicitation**: Invoke **[/forge-ba](./forge-ba.md)** for high-level requirement analysis.
2. **Master Planning**: Trigger **[/forge-plan](./forge-plan.md)** (Hard mode) to create the fundamental architecture.
3. **Trigger**: `trigger-session-start` initializes the environment and context.

### Phase 2: Infrastructure & Scaffolding

1. **Infra Blueprinting**: Invoke **[/ops-infra-plan](./ops-infra-plan.md)** for directory structures and dependencies.
2. **Secret Inception**: Trigger **[/ops-secrets](./ops-secrets.md)** for the initial vault setup.
3. **Git Genesis**: Invoke **[/forge-git](./forge-git.md)** for the initial commit and branch strategy.

### Phase 3: Core Implementation (Initial Cook)

1. **Sub-module Forge**: Trigger **[/forge](./forge.md)** for the first implementation cycle.
2. **UI/UX Seed**: Launch **[/forge-ui-ux](./forge-ui-ux.md)** for the design system.
3. **Early Verification**: Continuous **[/forge-test](./forge-test.md)** execution.

### Phase 4: Quality Lock & Governance

1. **Forensic Audit**: Invoke **[/forge-review](./forge-review.md)** on the entire bootstrap artifact.
2. **Registry Mapping**: Pulse **[/forge-docs](./forge-docs.md)** to ingest the new project into the Master Index.
3. **Trigger**: `trigger-task-logger` records the formal feature launch.

## 3. Iron Laws

- **Foundation-First**: No implementation without a 100% approved architectural plan.
- **ISO Purity**: Initial bootstrap must achieve a 10/10 quality score with zero technical debt (Zero-Tolerance).
- **Communication Standards**: All initial code comments and project docs must be in English.
