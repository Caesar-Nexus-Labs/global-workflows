---
name: forge-finish-branch
description: Automated branch completion workflow with 2-layer architecture validation, security verification, code review, encryption, and merge orchestration
category: forge
status: production
methodology: deterministic
---

# /forge-finish-branch — Automated Branch Completion with 2-Layer Architecture Validation

## Overview

Complete a feature or bugfix branch with comprehensive security verification, architecture debt tracking, code review integration, encryption, and automated merge. This workflow enforces a 2-layer architecture analysis to detect debt before merge and provides human decision gates at critical points.

## Workflow Phases

### Phase 0: Security Verification

**Purpose:** Classify code and verify it against security policies before processing.

**Actions:**
- Detect code classification (public/proprietary/confidential) from file headers and path conventions
- Check secrets manager policy for security classification requirements
- Scan for hardcoded secrets/credentials using built-in patterns
- Verify no breaches of data sensitivity policies
- Reject branch if: confidential code in public directory, hardcoded secrets detected, or policy violated

**Exit Points:**
- **PROCEED:** Code passes security classification
- **BLOCK:** Security policy violation → human review required
- **ESCALATE:** Suspicious patterns detected → notify security team

**Output:** Security clearance certificate (logged to .security-log)

---

### Phase 0B: Architecture Analysis (2-Layer)

**Purpose:** Auto-detect architectural debt and provide human decision gate.

**Layer 1: Automatic Detection** — Scan diff for debt patterns:
- Circular dependencies → `TYPE:CIRCULAR_DEP`
- God objects (>500 lines) → `TYPE:GOD_OBJECT`
- Missing error handling → `TYPE:ERROR_HANDLING`
- SOLID violations → `TYPE:SOLID_VIOLATION`
- N+1 queries → `TYPE:QUERY_INEFFICIENCY`
- Deprecated API usage → `TYPE:DEPRECATED_API`
- Tech debt markers (FIXME, TODO, HACK) → `TYPE:DEBT_MARKER`
- Module coupling → `TYPE:MODULE_COUPLING`

**Layer 2: Human Decision Gate** — If debt > threshold (> 3 issues OR severity > MEDIUM):
- Pause and notify reviewer
- Reviewer decides: ACCEPT_DEBT / REQUEST_FIXES / ESCALATE

**Logging:** All findings logged to `.arch-debt-log`

**Output:** Architecture clearance certificate

---

### Phase 1: Verification

**Purpose:** Run `/forge-verify-done` to validate branch readiness.

**Actions:** Build succeeds, all tests pass, no lint errors, coverage threshold met, docs updated, commit messages follow convention.

**Exit Points:** PROCEED / BLOCK (show failure report) / ESCALATE

**Output:** Verification report with checksums

---

### Phase 2: Code Review

**Purpose:** Human code review via `/code-review` workflow.

**Actions:** Logic correctness, test coverage, performance, security analysis, style, docs quality, breaking changes detection.

**Exit Points:** APPROVE / REQUEST_CHANGES / ESCALATE

**Output:** Code review approval/rejection with comments

---

### Phase 2B: Architecture Debt Decision

**Purpose:** Human reviewer decides on detected architectural debt.

**Triggered when:** Layer 1 detected debt exceeding threshold.

**Reviewer decides:**
- **ACCEPT_DEBT:** Document reasoning, proceed
- **REQUEST_FIXES:** Return to author for refactoring
- **DEFER:** Mark for future sprint, allow merge with tracking
- **ESCALATE:** Send to architecture committee

**Constraints:** Cannot approve SECURITY debt; HIGH severity requires 2 approvers.

**Output:** Debt decision record (appended to .arch-debt-log)

---

### Phase 3: Encryption

**Purpose:** Encrypt sensitive branch data.

**Actions:** Check if encryption is initialized, encrypt `.env.*` files and secrets manager configs, verify encryption integrity, store encryption metadata in branch.

**Exit Points:** PROCEED / SKIP (no sensitive files) / BLOCK (encryption failure)

**Output:** Encryption manifest (metadata only, no keys stored)

---

### Phase 4: Merge

**Purpose:** Merge branch into target using merge-commit strategy.

**Actions:** Use merge-commit (NOT squash, NOT rebase) to preserve history, tag merge commit, update CHANGELOG.md if maintained.

**Merge commit format:**
```
Merge branch 'feature/name' (closes #issue)

- Summary of changes
- Phase 2B decision (if applicable)
- Debt tracking reference (if applicable)
- Sign-off by reviewers
```

**Exit Points:** PROCEED / CONFLICT (manual resolution) / BLOCK (protection rules)

**Output:** Merge commit hash and metadata

---

### Phase 5: Cleanup

**Purpose:** Clean up working artifacts (branch, worktree, logs).

**Actions:** Delete remote + local branch, remove worktree, archive logs, clean temp files, close GitHub issues.

**Exit Points:** COMPLETE / PARTIAL / MANUAL

**Output:** Cleanup report with artifact preservation paths

---

## Iron Laws

1. **Security Cannot Be Skipped** — Phase 0 always runs. Hardcoded secrets ALWAYS block merge. No exceptions without security team approval.
2. **Architecture Debt Is Tracked Forever** — Every decision logged to `.arch-debt-log`. Quarterly reviews mandatory.
3. **Code Review Is Non-Negotiable** — At least 1 approval required. Approver must review all changes.
4. **Merge Commits Preserve History** — Never squash or rebase. Enables accurate bisect and blame.
5. **Cleanup Is Mandatory** — Phase 5 always completes even if workflow fails earlier.
6. **Human Decisions Override Automation** — Phase 2B requires human approval. Decision always logged with reasoning.
7. **Encryption Preserves Integrity** — Keys never stored in artifacts. Encryption failures block merge.

---

> Extended detail (parameters, examples, metrics, troubleshooting): see `_internal/forge-finish-branch-detail.md`
