---
description: Bootstrap a new project or implement major feature from zero with full orchestration.
---

# Project Bootstrap (/forge-bootstrap)

## 1. Description

The "Genesis Command". Orchestrates the birth of a new project or major feature from zero, ensuring the foundation is structurally sound and follows Caesar Nexus standards.

For workspace-managed sessions, this command is the only authority allowed to create a new linked workspace. Opening an existing folder, opening a `.code-workspace` file, or switching client transport must attach to an existing workspace instead of creating one implicitly.

## 2. Command Syntax

```bash
/forge-bootstrap [workspace-name-or-requirement]
```

- With no argument: create a new linked workspace using system defaults and an auto-generated name.
- With an argument: use it as the preferred workspace or feature label.
- If invoked inside an already linked workspace: resume the current workspace and continue bootstrap in-place.

## 3. Workspace Binding Gate

### Creation Authority

- Only an explicit `/forge-bootstrap` invocation may create a linked workspace.
- No other slash command may create a workspace implicitly.
- Opening a folder or workspace file is attach/resume behavior only.

### Idempotent Bootstrap

- If an active binding already exists for the current human workspace, `/forge-bootstrap` must attach and continue instead of spawning a duplicate.
- If no binding exists, `/forge-bootstrap` may create exactly one new linked workspace set.

### Binding Artifacts

When a new linked workspace is created, generate:

1. Human workspace root: `<workspace-root>/<name>`
2. Active execution workspace: `CAESAR_ROOT/workspace-state/active/ws-<timestamp>-<name>`
3. Metadata binding: `<workspace-root>/<name>/.nexus/workspace.json`
4. Workspace launcher: `<workspace-root>/<name>/Open-<name>.code-workspace`

### Default Bootstrap Values

- Runtime source: `caesar-runtime`
- Preferred route: `direct`
- Fallback route: `omni`

## 4. Caesar Nexus Execution Loop

### Phase 0: Binding & Session Gate

1. **Invocation Check**: Confirm the request is an explicit `/forge-bootstrap`.
2. **Binding Detection**:
   - If linked: attach/resume only.
   - If unlinked: create the binding artifacts once, then continue.
3. **Creation Guard**: Block duplicate creation if a linked workspace already exists for the target root.
4. **Trigger**: `trigger-session-start` initializes the environment after binding is resolved.

### Phase 1: Genesis & Blueprinting

1. **Initial Elicitation**: Invoke **[/forge-ba](./forge-ba.md)** for high-level requirement analysis.
2. **Master Planning**: Trigger **[/forge-plan](./forge-plan.md)** (Hard mode) to create the fundamental architecture.
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

## 5. Iron Laws

- **Explicit Creation Gate**: Only an explicit `/forge-bootstrap` call may create a new linked workspace.
- **Open-Is-Not-Create**: Opening folders or workspace launchers must never create a workspace.
- **Idempotent Binding**: If a workspace is already linked, `/forge-bootstrap` must resume it instead of spawning a duplicate.
- **Foundation-First**: No implementation without a 100% approved architectural plan.
- **ISO Purity**: Initial bootstrap must achieve a 10/10 quality score with zero technical debt (Zero-Tolerance).
- **Communication Standards**: All initial code comments and project docs must be in English.
