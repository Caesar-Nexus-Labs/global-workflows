# /forge-execute-plan

> **Plan Execution Orchestrator** — Execute pre-written implementation plans phase-by-phase.

---

## Metadata

| Field | Value |
|-------|-------|
| **Slug** | `/forge-execute-plan` |
| **Type** | Execution Orchestrator |
| **Conductor Agents** | Developer, Tester, Release Manager |
| **Prerequisites** | Plan document approved by user (from `/forge-plan`) |
| **Execution Mode** | EXECUTION ONLY (no planning, no brainstorming) |

---

## Description

`/forge-execute-plan` orchestrates the **execution phase** of implementation plans created by `/forge-plan`. It is the primary entry point for turning finalized plans into working implementations.

**This command ONLY executes pre-written plans. Planning happens separately in `/forge-plan`.**

---

## Critical Separation

```
/forge-brainstorm → (ideas only, no execution)
    ↓
/forge-plan → (plan writing only, no execution)
    ↓ [USER REVIEWS & APPROVES]
    ↓
/forge-execute-plan → (execution only, no planning)
```

---

## Prerequisites

Before calling `/forge-execute-plan`, user MUST:
1. Have run `/forge-plan` and received approved plan document
2. Reviewed plan for correctness and feasibility
3. Obtained plan approval (user decision)
4. Ready to proceed with implementation

---

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| `--plan-file` | string | Path to approved plan.md (required) |
| `--dry-run` | boolean | Preview changes without execution (default: false) |
| `--phase` | string | Start from specific phase (default: phase-01) |
| `--stop-on-error` | boolean | Halt if any step fails (default: true) |
| `--notify-channel` | string | Slack/Discord channel for progress updates |

---

## Execution Logic

### Phase Execution Loop

```bash
FOR EACH phase-XX-*.md in plan:
  1. Validate phase prerequisites
  2. Execute phase steps sequentially
  3. Run tests/verification for phase
  4. If failure: HALT or SKIP (based on --stop-on-error)
  5. Log phase completion to /forge-journal
  6. Checkpoint state for rollback capability
END

FINAL: Generate execution summary report
```

### Per-Phase Execution

Each phase (`phase-01-core.md`, `phase-02-integration.md`, etc.) executes:
1. Code changes (file writes, refactoring)
2. Tests (TDD verification)
3. Quality gates (lint, type-check via triggers)
4. Integration checks
5. Documentation updates

---

## Allowed Operations

✅ **Only in /forge-execute-plan**:
- File writes and code changes
- Tool/MCP execution
- Deployment operations
- Subagent spawning for parallel work
- Implementation automation
- All execution-phase commands: `/forge-test`, `/forge-refactor`, `/forge-clean`, `/forge-git`, etc.

🚫 **NEVER in /forge-execute-plan**:
- Planning or design changes (use `/forge-plan`)
- Brainstorming (use `/forge-brainstorm`)
- Re-architecting without new plan

---

## Output Format

```json
{
  "execution_id": "exec-feature-auth-20260317",
  "plan_file": "plan.md",
  "phases_total": 8,
  "phases_completed": 8,
  "status": "success|partial|failed",
  "duration_ms": 450000,
  "changes_made": {
    "files_created": 12,
    "files_modified": 24,
    "files_deleted": 2
  },
  "tests_run": 156,
  "tests_passed": 156,
  "errors": [],
  "summary": "All phases completed successfully. 38 files changed."
}
```

---

## Related Commands

- [/forge-plan](forge-plan.md) — Plan generation (MUST run before this)
- [/forge-brainstorm](forge-brainstorm.md) — Ideation (input to /forge-plan)
- [/forge-test](forge-test.md) — TDD execution during phases
- [/forge-refactor](forge-refactor.md) — Code optimization during execution
- [/forge-git](forge-git.md) — Version control during execution
- [/forge-journal](forge-journal.md) — Progress logging

---

## Example Workflow

```bash
# Step 1: User creates plan (NOT in this command)
$ /forge-plan --requirements "Add OAuth 2.0 authentication"
→ Outputs: plan.md, phase-01-core.md, phase-02-integration.md, phase-03-tests.md

# Step 2: User reviews and approves plan
$ # ... user reads plan.md and decides to proceed

# Step 3: User executes plan (THIS command)
$ /forge-execute-plan --plan-file plan.md
→ [PHASE 1] Core auth implementation... ✅
→ [PHASE 2] Integration with MCP services... ✅
→ [PHASE 3] Test suite execution... ✅ (156/156 passed)
→ EXECUTION COMPLETE

Execution ID: exec-auth-20260317-145632
Duration: 450 seconds
```

---

## Failure Handling

### Stop-On-Error Mode (default)
- Any phase failure → HALT immediately
- Rollback to last checkpoint
- Report error and required fixes
- User decides: re-run or abandon

### Continue-On-Error Mode (--stop-on-error=false)
- Phase failure → log and SKIP to next phase
- May result in partial implementation
- Use only if you understand consequences

---

**Status**: PROD-READY ✅
**Version**: 1.0.0
**Created**: 2026-03-17
