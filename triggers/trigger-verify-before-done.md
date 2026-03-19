---
name: trigger-verify-before-done
description: Auto-fires before any task completion claim — enforces evidence-based verification gate. Blocks "done" claims without fresh command output.
event: trigger-pre-completion
matcher: "completion_claim|task_done|mark_complete|status: completed"
logic_source: superpowers:verification-before-completion (adapted for Caesar Nexus)
---

# Trigger: Verify Before Done (`trigger-verify-before-done`)

## 1. Description

The "Completion Integrity Guard". Fires automatically whenever an agent is about to:
- Mark a task as `completed` in TodoWrite
- State "done", "fixed", "complete", "works", "passes", "all clear"
- Commit, push, or create a PR
- Hand off to the next agent or phase

**This trigger is the Caesar Nexus equivalent of `superpowers:verification-before-completion`.** It cannot be bypassed. No claim of completion is valid without fresh evidence.

---

## 2. Activation Conditions

This trigger fires on any of:

| Signal | Example |
|--------|---------|
| TodoWrite status → `completed` | Agent marks task done |
| Completion language | "Done!", "Fixed!", "Complete!", "All tests pass" |
| Handoff language | "Moving to next phase", "Handing off to..." |
| Pre-commit / pre-push | Git commit or push about to run |
| Agent task output | Subagent reports "success" |
| Satisfaction expression | "Great!", "Perfect!", "Looks good!" |

---

## 3. Execution Logic

### Step 1 — Intercept
Detect completion signal. **Pause** before the claim is made.

### Step 2 — Evidence Check
Ask: *Is there fresh verification evidence in the current message?*

```
Fresh evidence = command output from THIS message showing:
  - Exit code 0
  - Zero failures
  - Actual test/build/lint output text
```

**If YES** → evidence present → allow completion claim → proceed.

**If NO** → evidence missing → **BLOCK** → invoke `/forge-verify-done`.

### Step 3 — Mandatory Verification Run

Invoke **[/forge-verify-done](./forge-verify-done.md)** to run required verification commands.

Commands to run depend on task type:

| Task Type | Commands |
|-----------|----------|
| Rust code change | `cargo check && cargo test && cargo clippy -- -D warnings` |
| SvelteKit change | `pnpm build && pnpm check && pnpm lint` |
| Tauri app | `cargo check --manifest-path src-tauri/Cargo.toml && pnpm build` |
| Workflow/doc edit | Verify all cross-referenced file links exist |
| Agent delegation | `git diff HEAD` to confirm actual changes |
| Any test claim | Run test suite, read output, count failures |

### Step 4 — Gate Decision

```
ALL commands exit 0 AND zero failures?
  → YES: Unblock completion claim. Agent may proceed.
  → NO:  Block. Log failure evidence. Redirect to fix.
         Agent must fix + re-invoke trigger-verify-before-done.
```

### Step 5 — Log

On **PASS**: trigger **[trigger-task-logger](./trigger-task-logger.md)** with verification evidence payload.

On **FAIL**: log blocked attempt to `/forge-journal`, surface failure to agent for fix.

---

## 4. Iron Laws

- **Zero bypass**: No exception for urgency, prototype, or "just this once".
- **Cached output = invalid**: Evidence must be from the current message/run.
- **Partial verification = block**: Build passing alone is insufficient. All dimensions required.
- **Agent trust = zero**: Subagent "success" message does not satisfy this trigger. VCS diff or re-run required.
- **Regression = red-green**: Any regression test claim requires verified red (fails without fix) then green (passes with fix).

---

## 5. Integration

- **Invokes**: **[/forge-verify-done](./forge-verify-done.md)** for full verification gate
- **On pass → invokes**: **[trigger-task-logger](./trigger-task-logger.md)** for completion log
- **On fail → routes to**: **[/forge-debug](./forge-debug.md)** or **[/forge-problem-solving](./forge-problem-solving.md)**
- **Works alongside**: `trigger-rust-verify` (file-level), `trigger-lint` (lint-level) — this trigger is the **task-completion-level** gate
