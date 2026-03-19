---
name: trigger-lint
description: ISO standard code formatting using cargo fmt.
event: trigger-post-tool
matcher: ".*\\.rs$"
---

# Trigger: Lint (`trigger-lint`)

## 1. Description
Enforces "Clean Code" standards by automatically formatting Rust files using the official `cargo fmt` tool. It ensures all code follows Caesar Nexus style guides defined in `rustfmt.toml`.

## 2. Execution Logic
- **Invoke Event**: `trigger-post-tool`.
- **Action**:
    1. Run `cargo fmt -- --check` to identify violations.
    2. If violations exist, run `cargo fmt` to auto-fix immediately.
    3. Report success or unfixable errors to the session log.
- **Goal**: Zero overhead style management.

## 3. Iron Laws
- **Consistency**: Code must always be formatted before any `/forge-review` gate.
- **Ecosystem**: Must align with global Cargo workspaces configuration.
