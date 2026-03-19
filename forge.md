---
name: /forge
description: Primary development orchestration.
category: Engineering
status: Stable
methodology: Caesar Nexus Logic
---

# Feature Implementation (/forge)

## 1. Description
Orchestrates the entire development lifecycle from a raw requirement or an existing `plan.md` to production-ready, tested code. It acts as the "Implementation Conductor".

## 2. Command Syntax
```bash
/forge <task OR plan path> [flags]
```

## 3. Caesar Nexus Execution Loop

### Phase 1: Strategic Alignment
1. **Intent Detection**: Analyzes the request to choose between "Plan-first" or "Direct-cook" workflows.
2. **Research & Scout**: (If needed) Invoke **[/forge-scout](./forge-scout.md)** for deep codebase analysis.
3. **Plan Sync**: 
   - If a plan exists: Sync status. 
   - If missing: Trigger **[/forge-plan](./forge-plan.md)** to generate blueprints.
   - **Trigger**: `trigger-rules-reminder` ensures adherence to `forge-development-rules.md`.

### Phase 2: Implementation Cycle (TDD - Red/Green/Clean)
1. **Reproduction/Defense**: If debugging, invoke **[/forge-debug](./forge-debug.md)** first.
2. **Development**:
   - **TDD RED**: Write failing tests.
   - **TDD GREEN**: Minimal code to pass.
   - **Refactor**: Periodic invocation of **[/forge-refactor](./forge-refactor.md)** or **[/forge-clean](./forge-clean.md)**.
   - **Trigger**: `trigger-rust-verify` auto-executes on save to catch compilation errors early.
   - **Trigger**: `trigger-edit-tracker` monitors complexity accumulation.

### Phase 3: Quality Verification
1. **Automated Review**: Invoke **[/forge-review](./forge-review.md)** for a 6-agent forensic audit.
2. **Testing**: Trigger **[/forge-test](./forge-test.md)** for full regression suite. 100% pass mandatory.
3. **Trigger**: `trigger-lint` ensures zero formatting debt.

### Phase 4: Final Handoff & Ledger
1. **Documentation**: Invoke **[/forge-docs](./forge-docs.md)** to update the Master Index.
2. **Journaling**: Trigger `trigger-task-logger` to record decisions in **[/forge-journal](./forge-journal.md)**.
3. **Deployment Link**: Redirect to **[/ops-deploy](./ops-deploy.md)** for high-availability rollout.

## 4. Iron Laws
- **Chain of Custody**: Every code change must be traceable back to a `/forge-plan` step.
- **Zero Skeletal Policy**: No placeholders (`TODO`, `FIXME`). All code must be finalized.
- **Standardized Communication**: All internal logging and AI-facing comments must follow ISO standard (English).
