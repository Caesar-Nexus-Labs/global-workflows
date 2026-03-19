---
name: /forge-verify-done
description: Evidence-based completion gate — runs build/test/lint commands and reads full output before any "done" claim is made. Blocks completion without fresh verification evidence.
category: Quality & Verification
status: Stable
methodology: Caesar Nexus Logic
---

# Completion Verification Gate (/forge-verify-done)

> **THE IRON LAW**: No completion claim without fresh verification evidence.
>
> If you haven't run the verification command **in this message**, you cannot claim it passes.
> **"Should work"** ≠ evidence. **"Looks correct"** ≠ evidence. **Run the command. Read the output. Then claim.**

---

## 1. Description

The "Evidence Gate". A mandatory verification checkpoint invoked **before any claim of completion, correctness, or success**. Enforces the discipline of running real commands, reading real output, and reporting real state — never extrapolating, never assuming.

This is the Caesar Nexus equivalent of `superpowers:verification-before-completion`. It applies to every task in every kit: Engineering, Marketing, DevOps, and Agent work.

---

## 2. The Gate Function

```
BEFORE claiming any status or expressing satisfaction:

1. IDENTIFY — What command proves this claim?
2. RUN     — Execute the FULL command (fresh, never cached)
3. READ    — Full output: exit code, error count, pass count
4. VERIFY  — Does output confirm the claim?
           → NO:  State actual status with evidence
           → YES: State claim WITH evidence quoted
5. CLAIM   — Only now may a completion statement be made
```

**Skip any step = false claim. False claims are integrity violations.**

---

## 2. Caesar Nexus Execution Loop

### Phase 1: Claim Detection
1. **Trigger Scan**: Is the agent about to state "done", "complete", "fixed", "passes", "works", "clean"? If yes → **mandatory gate activation**.
2. **Scope Check**: What was the task? What are the verifiable success criteria?
3. **Command Identification**: Per the table below, identify which command(s) prove the claim.

### Phase 2: Evidence Collection (MUST RUN FRESH)
1. **Execute verification commands** — never rely on previous run output.
2. **Read full output** — do not skim. Count failures. Read exit codes.
3. **Check all dimensions**: build + test + lint — each independently.
   - If any dimension fails → task is NOT complete.
4. **Agent verification**: If a subagent reported success → check VCS diff or run independently.

### Phase 3: State Reporting
1. **Evidence-first**: Quote exact output (exit code, pass/fail count) before making any claim.
2. **If passing**: State `✅ [command] → [output summary]` then make completion claim.
3. **If failing**: State actual status with evidence. Update task as `in_progress`. Fix and re-invoke `/forge-verify-done`.
4. **Requirements check**: Before final sign-off, re-read original requirements line by line. Report any gaps.

### Phase 4: Completion Gate (CONDITIONAL)
- **PASS**: All verification commands exit 0, zero failures → completion claim allowed.
- **FAIL**: Any failure → block completion, fix issue, restart from Phase 2.
- **PARTIAL**: Partial check is insufficient. All dimensions must pass.

---

## 3. Verification Command Reference

| Claim | Required Command | Not Sufficient |
|-------|-----------------|----------------|
| Rust code works | `cargo check` or `cargo build` | Linter passing, code "looks right" |
| Tests pass | `cargo test` / `pnpm test` / `vitest run` | Previous run, "should pass" |
| Linter clean | `cargo clippy` / `pnpm lint` | "I reviewed it manually" |
| SvelteKit build | `pnpm build` exit 0 | TypeScript "looks fine" |
| TypeScript valid | `pnpm check` (svelte-check) | IDE no errors |
| Bug fixed | Test original symptom + regression test | Code changed |
| Agent completed | VCS diff shows actual changes | Agent reports "success" |
| Spec met | Line-by-line checklist vs requirements | Tests passing |
| File written | `cat file` output visible | "I wrote it" |
| Link valid | File exists check | "I referenced it" |

---

## 4. Red Flag Phrases — STOP IMMEDIATELY

If you are about to write any of these — **stop and run verification first**:

- "should work now" / "should pass"
- "looks correct" / "looks good"
- "Done!" / "Complete!" / "Fixed!" / "Perfect!"
- "I've implemented..." (without running build)
- "All tests pass" (without running tests in this message)
- "No errors" (without running linter in this message)
- "The bug is fixed" (without testing original symptom)
- "Agent reported success"
- "I'm confident this works"

**These are rationalization traps. The antidote is running the command.**

---

## 5. Iron Laws

- **Evidence before claims**: No completion statement without command output in the same message.
- **No cached evidence**: A run from 5 minutes ago is not fresh. Run again.
- **No partial verification**: Build passing ≠ tests passing. All dimensions required.
- **No agent trust**: Subagent "success" reports must be independently verified via VCS diff or re-run.
- **No exceptions for urgency**: "We're in a hurry" is not a bypass. Fast failures are faster than silent failures in production.
- **Regression tests are Red-Green**: Write test → verify it FAILS on broken code → apply fix → verify it PASSES. Skipping the RED phase means the test proves nothing.
- **English Standard**: All verification reports and evidence logs in English.

---

## 6. Integration Points

- **Called by**: `trigger-verify-before-done` (auto-fires), any agent before claiming task complete
- **Calls**: `trigger-task-logger` to record verified completion
- **After passing**: Log completion to **[/forge-journal](./forge-journal.md)**
- **If failing**: Redirect to **[/forge-debug](./forge-debug.md)** or **[/forge-problem-solving](./forge-problem-solving.md)**
- **For code reviews**: Combine with **[/forge-review](./forge-review.md)** (design) and **[/code-review](./forge-review.md)** (code)

---

## 7. Execution Flow

```
AGENT is about to claim "done" / "fixed" / "complete"
  │
  ├─► GATE ACTIVATION (mandatory)
  │
  ├─► PHASE 1: Identify claim + verification commands
  │
  ├─► PHASE 2: Run commands FRESH
  │   ├─ cargo check / cargo test / cargo clippy
  │   ├─ pnpm build / pnpm test / pnpm lint
  │   └─ Custom commands per project
  │
  ├─► PHASE 3: Read output
  │   ├─ Exit code = 0? ──── NO ──► Fix → restart Phase 2
  │   ├─ Failures = 0? ──── NO ──► Fix → restart Phase 2
  │   └─ Requirements met? ── NO ──► Fix → restart Phase 2
  │
  ├─► PHASE 4: ALL PASS
  │   ├─ Quote evidence: "cargo test: 34/34 pass, exit 0"
  │   └─ Make completion claim WITH evidence
  │
  └─► Log to /forge-journal + trigger-task-logger

ONLY THEN: Task is marked complete
```
