---
name: /forge-port-feature
description: Use when you need to port full or partial feature logic from another module or codebase. Rewrites code using TDD, enforces project code style, and requires human approval of dependency groups before implementation begins.
category: Feature Development
status: Stable
methodology: Caesar Nexus Logic
---

# Feature Port Workflow (/forge-port-feature)

## 1. Description

Port full or partial feature logic from a source module into the current project. Never copy-paste code verbatim — always rewrites from scratch using TDD. Enforces strict project code style. Human must approve dependency groups before implementation begins.

## 2. Command Syntax

```bash
/forge-port-feature <source-path> [--scope=full|partial] [--from=<repo-url>]
```

**Flags:**
- `--scope=full` (default) — Port entire module as analyzed
- `--scope=partial` — Human specifies which parts during Phase 2
- `--from=<repo-url>` — Source from external repo (clones to temp dir, cleaned up after Phase 1)

## 3. Caesar Nexus Execution Loop

### Phase 0: Remote Source Setup (only when `--from` is present)

1. Clone `--from=<repo-url>` to `tmp/port-source-{feature}-{date}/`
2. Scope analysis to `<source-path>` within cloned repo
3. **After Phase 1 completes → delete `tmp/port-source-*` (Zero Orphan Policy)**

### Phase 1: Source Analysis

- **Call**: `/forge-scout`
- **Action**: Scan source module — extract logic, design patterns, interfaces, full dependency tree
- **Classify dependencies** into groups:
  - `auth-deps` — authentication related
  - `db-deps` — database/storage related
  - `util-deps` — utility helpers
  - `domain-deps` — business logic dependencies
  - `infra-deps` — infrastructure concerns
  - `test-deps` — test utilities
- **Output**: `reports/port-analysis-{feature}-{date}.md` (full dep tree + grouped + code style diff)

### Phase 2: Human Decision Gate

Workflow **PAUSES** and presents the full port analysis report:

```
PORT ANALYSIS REPORT: {feature}
==============================

FULL DEPENDENCY LIST ({N} items):
  auth-deps (N):    [...]
  db-deps (N):      [...]
  util-deps (N):    [...]
  domain-deps (N):  [...]
  infra-deps (N):   [...]
  test-deps (N):    [...]

SCOPE: [ ] full — Port entire module as analyzed
       [ ] partial — Select specific parts

DEPENDENCY APPROVAL (approve/reject by group):
  [ ] auth-deps    [ ] db-deps    [ ] util-deps
  [ ] domain-deps  [ ] infra-deps [ ] test-deps
```

**Rejected group handling (deterministic):**
- `domain-deps` or `auth-deps` or `db-deps` or `infra-deps` rejected → **PAUSE**: human decides skip vs. lightweight reimplementation
- `util-deps` or `test-deps` rejected → **AUTO**: lightweight reimplementation (no pause)

**Output**: `reports/port-plan-{feature}-{date}.md` (confirmed scope + approved deps)

### Phase 3: Implementation (TDD)

- **Call**: `/forge-cook`
- **Iron Law**: ZERO verbatim copy-paste from source — every line rewritten
- **Per unit cycle**:
  1. **TDD RED** — Write failing test
  2. Run → verify fails with expected error
  3. **TDD GREEN** — Write minimal code to pass
  4. Run → verify passes
  5. **REFACTOR** — Apply `forge-development-rules.md` style
  6. **Legacy reference scan** — detect and fail if found:
     - Import paths from source namespace
     - Source-project naming prefixes/suffixes
     - Verbatim function/struct names not adapted
     - String literals referencing source project
  7. Run tests → verify still passing
  8. Commit atomic change

### Phase 4: Integration Testing

- **Call**: `/forge-test`
- **Actions**:
  1. Test integration points with existing modules
  2. Verify no breaking changes to existing API surface
  3. Test approved dependencies work correctly
  4. Run full test suite
  5. Check for circular dependencies introduced by port
- **Gate**: All integration tests pass before proceeding

### Phase 5: Review & Handoff

1. **Call**: `/code-review` — quality score ≥ 9.5, zero critical issues
2. **Call**: `/forge-docs` — update documentation
3. Append to `.port-history.log`:
   ```
   {date} | {feature} | {scope} | {approved-dep-groups} | {commit-hash}
   ```
4. **Call**: `/forge-finish-branch` — safe merge with 2-layer architecture gate

## 4. Integration Map

```
/forge-ba (optional)         → clarify business requirements for port
/forge-scout                 → Phase 1 (source analysis)
/forge-port-feature          → THIS WORKFLOW (phases 0-5)
  └─ /forge-cook (TDD)       → Phase 3 implementation
  └─ /forge-test             → Phase 4 integration
  └─ /code-review            → Phase 5 quality gate
  └─ /forge-finish-branch    → Phase 5 merge

Note: /forge-plan may be invoked manually BEFORE this workflow to pre-design
integration strategy. It is NOT part of the automated chain.
```

## 5. Iron Laws

1. **Zero Verbatim Copy** — Every line of code must be rewritten. No copy-paste from source.
2. **Full Audit First** — Complete dependency tree listed before any implementation begins.
3. **Human Gate Required** — Implementation cannot begin without explicit approval of dependency groups.
4. **Strict Style Enforcement** — `forge-development-rules.md` is the authority on code style. No exceptions.
5. **TDD Mandatory** — Every ported unit must have a failing test before implementation.
6. **No Scope Creep** — Port only what was approved. Unapproved features require a new port cycle.
7. **Atomic Commits** — One unit per commit. No bulk commits.
8. **Zero Orphan** — Temp clone directories must be deleted after Phase 1.

## 6. File Outputs

| File | Phase | Purpose |
|------|-------|---------|
| `reports/port-analysis-{feature}-{date}.md` | 1 | Full dependency tree + style diff |
| `reports/port-plan-{feature}-{date}.md` | 2 | Confirmed scope + approved deps |
| `.port-history.log` | 5 | Audit log: one line per completed port |
| `tmp/port-source-{feature}-{date}/` | 0 | Temp clone (deleted after Phase 1) |

## 7. Example Usage

```bash
# Port full auth module from local project
/forge-port-feature src/auth --scope=full

# Port only the JWT validation logic
/forge-port-feature src/auth/jwt --scope=partial

# Port from external repo
/forge-port-feature src/payments --from=github.com/org/payments-service

# Port partial feature from external repo
/forge-port-feature src/notifications/email --scope=partial --from=github.com/org/notification-service
```
