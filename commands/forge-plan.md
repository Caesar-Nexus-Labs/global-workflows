---
description: Generates high-fidelity project blueprints and implementation plans (PLANNING ONLY - NO EXECUTION).
execution_mode: PLAN WRITING ONLY - NO EXECUTION
---

# Project Planning (/forge-plan)

> ⚠️ **CRITICAL**: `/forge-plan` is a PLAN WRITING command.
> - **PLANNING ONLY** — Generate blueprints, phases, and strategy documents
> - **NEVER EXECUTE** — No code changes, no deployments, no implementation
> - **HANDOFF ONLY** — Output plan documents for user review
> - **REDIRECT TO /forge-execute-plan** — User decides when to execute
> - For execution, call `/forge-execute-plan` (separate command)

## 1. Description

Generates high-fidelity project blueprints comprising a `plan.md` overview and interactive `phase-XX-*.md` implementation files. It is the "Strategic Nerve Center" of any feature.

**This command ONLY writes plans. Execution happens in `/forge-execute-plan`.**

## 2. Command Syntax

```bash
/forge-plan <requirements> [flags]
```

## 3. Caesar Nexus Execution Loop

### Phase 1: Reconnaissance & Ideation

1. **Context Discovery**: Invoke **[/forge-scout](./forge-scout.md)** to map existing dependencies and patterns.
2. **Adversarial Ideation**: (Optional) Trigger **[/forge-brainstorm](./forge-brainstorm.md)** to find the most innovative architectural path.
3. **Trigger**: `trigger-rules-reminder` ensures early alignment with `forge-development-rules.md`.

### Phase 2: Blueprint Architecture

1. **Specification Sync**: If starting from a spec, sync with **[/spec-create](./spec-create.md)**.
2. **Decomposition**: Break requirements into atomic, checkable phases (`phase-01-core.md`, etc.).
3. **Research Depth**: Launch **[/forge-research](./forge-research.md)** for any unproven technical stacks.

### Phase 3: Technical Validation & Review

1. **Red Team Audit**: Invoke **[/forge-review](./forge-review.md)** on the plan itself (Logic-only review).
2. **Constraint Check**: Verify against `mcp_config.json` and system resource limits.
3. **Trigger**: `trigger-edit-tracker` marks the start of a major complexity increment.

### Phase 4: Plan Finalization & Handoff (NO EXECUTION)

1. **Plan Document Generation**: Create `plan.md` with approved phases and success criteria.
2. **Output Only**: Output finalized plan document for user review.
3. **Handoff Metadata**: Document suggested next step: **[/forge-execute-plan](./forge-execute-plan.md)** (user initiates this, not /forge-plan).
4. **Journaling**: SUGGEST logging to **[/forge-journal](./forge-journal.md)** (user does it, not /forge-plan).

**STOP HERE. Do NOT proceed to execution. User reviews plan and decides next step.**

## 4. Execution Boundaries (STRICT)

### PLANNING PHASE (What /forge-plan DOES)
- ✅ Call `/forge-scout`, `/forge-brainstorm`, `/forge-research` (context gathering)
- ✅ Call `/forge-review` on plan design only (no code changes)
- ✅ Generate plan documents (plan.md, phase-XX-*.md)
- ✅ Output finalized strategy document for user review
- ✅ Suggest `/forge-execute-plan` as next step (do NOT call it)

### EXECUTION PHASE (What /forge-plan NEVER DOES)
- 🚫 NO CODE CHANGES — Never modify files
- 🚫 NO DEPLOYMENTS — Never apply infrastructure changes
- 🚫 NO TOOL EXECUTION — Never run implementations
- 🚫 NO SUBAGENT SPAWNING — Never launch parallel agents
- 🚫 NEVER CALL /forge-execute-plan — User initiates execution separately

## 5. Iron Laws

- **Plan-First Discipline**: All planning happens in `/forge-plan`. Execution is separate (`/forge-execute-plan`).
- **Zero Ambiguity**: Each testable step must have clear success criteria in plan documents.
- **User Review Gate**: Plan MUST be reviewed and approved by user before any execution.
- **Separation of Concerns**: `/forge-plan` outputs document. `/forge-execute-plan` executes it. Never mix.
