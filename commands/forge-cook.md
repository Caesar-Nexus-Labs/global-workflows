---
name: /forge
description: Orchestrates the entire development lifecycle from a raw requirement or an existing plan.md to production-ready, tested code.
category: Feature Development
status: Stable
methodology: Caesar Nexus Logic
---

# Feature Implementation (/forge)

## 1. What This Workflow Does
Orchestrates the entire development lifecycle from a raw requirement or an existing `plan.md` to production-ready, tested code. It acts as the "Implementation Conductor".

## 2. Command Syntax
```bash
/forge <task OR plan path> [flags]
```
### Optional Flags
- `--auto`: Skips manual approval gates; ideal for routine tasks.
- `--fast`: Optimized for speed; reduces research depth.
- `--parallel`: Concurrent execution for cross-module features.
- `--no-test`: Skips the TDD cycle (Forbidden for core business logic).
- `--interactive`: (Default) Stops at major gates for architect review.

## 3. Caesar Nexus Execution Loop
1. **Intent Detection**: Analyzes the request to choose between "Plan-first" or "Direct-cook" workflows.
2. **Research & Scout**: (If needed) Parallel discovery of technical requirements and codebase context.
3. **Plan Sync**: If a plan exists, sync task status. If not, trigger `/forge-plan`.
4. **Implementation Cycle**:
   - **TDD RED**: Write a failing test for the current atomic task.
   - **TDD GREEN**: Minimal code to pass the test.
   - **Refactor**: Clean up and optimize following `forge-development-rules.md`.
   - **Trigger**: `trigger-rust-verify` auto-executes on save.
   - **Trigger**: `trigger-lint` ensures formatting.
5. **Quality Verification**:
   - **Automated Review**: Continuous linting and logic verification.
   - **Peer Agent Review**: Optional second agent audit (Hard mode).
6. **Final Pass**: Run the full test suite. 100% pass required.
7. **Handoff**: `project-manager` verifies completion; `docs-manager` updates references.
    - **Trigger**: `trigger-task-logger` records the win to `forge-journal.md`.
    - **Next Link**: Invoke `/ops-deploy` for production rollout.

## 4. Quality Gates
- **Testing**: 100% pass rate is mandatory for entry to the review phase.
- **Review Score**: Code must achieve a quality score of ≥ 9.5/10 with 0 critical issues.
- **Branding**: Mandatory check for `Caesar Nexus` alignment (Zero legacy references).

## 5. Iron Laws
- **No Skeletal Code**: All implementations must be functional and finalized.
- **Plan Adherence**: Never exceed the scope defined in the active `plan.md` without updating the plan.
- **ISO Standard**: All internal log messages and code comments must be in English.

