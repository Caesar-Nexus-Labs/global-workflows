---
description: Forensic debugging process proving the root cause before attempting a fix.
---

# Systematic Debugging (/forge-debug)

## 1. Description

Forensic debugging process proving the root cause before attempting a fix. It is the "Detective Conductor" for system instability.

## 2. Caesar Nexus Execution Loop

### Phase 1: Forensic Triage

1. **Incident Scoping**: Analyze logs and environment data.
2. **Reproduction Seed**: Create a minimal environment to isolate the bug.
3. **Deep Scouting**: Invoke **[/forge-scout](./forge-scout.md)** to find the exact line/logic block responsible.
4. **Trigger**: `trigger-edit-tracker` monitors if the bug is caused by recent complexity increments.

### Phase 2: Root Cause Proof (Reproduction)

1. **Failing Test Creation**: Trigger **[/forge-test](./forge-test.md)** with a "Red" test case that reliably proves the bug.
2. **Logic Modeling**: Use **[/forge-problem-solving](./forge-problem-solving.md)** to understand why the current logic fails.

### Phase 3: Correction & Defense

1. **Implementation**: Invoke **[/forge](./forge.md)** to apply the fix following the TDD Red/Green cycle.
2. **Simplification**: Redirect to **[/forge-refactor](./forge-refactor.md)** to ensure the fix doesn't add unnecessary complexity.
3. **Trigger**: `trigger-rust-verify` ensures the fix compiles flawlessly.

### Phase 4: Final Verification & Closure

1. **Regression Audit**: Trigger a full **[/forge-web-testing](./forge-web-testing.md)** (if UI) or unit suite.
2. **Ledger Update**: Record findings in **[/forge-journal](./forge-journal.md)**.
3. **Documentation Persistence**: Invoke **[/forge-docs](./forge-docs.md)** to update the "Known Issues" or "Gotchas" section.

## 3. Iron Laws

- **Evidence-First**: No fix shall be applied without a successful, standalone reproduction case.
- **Defense-in-Depth**: Every fix must include a guard/assertion to prevent the same bug from reappearing.
- **Zero Placeholder Fixes**: No hacks or "Quick-fixes" allowed. Solve the root cause or don't commit.
