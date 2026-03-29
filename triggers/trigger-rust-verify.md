---
name: trigger-rust-verify
description: High-fidelity Rust verification (cargo check + sccache).
event: trigger-post-tool
matcher: ".*\\.rs$"
logic_source: Caesar Nexus Logic (RE-ENGINEERED for RUST)
---

# Trigger: Rust Verify (`trigger-rust-verify`)

## 1. Description (Quantum Rust Logic)
Enforces strict Rust type checking and static analysis immediately after a tool modifies `.rs` files. It leverages global system standards (lld, sccache, threads=36) to maintain "Quantum-Speed" compilation.

## 2. Execution Logic
- **Matcher**: `Edit`, `Write`, `MultiEdit` on Rust files.
- **Action**:
    1. Invoke `cargo check --message-format=json` with parallel frontend enabled.
    2. Env: `RUSTFLAGS="-Z threads=36"`, `RUSTC_WRAPPER="sccache"`.
    3. Capture JSON diagnostics and parse for `error` and `warning` levels.
    4. Inject results into agent context for immediate correction if errors > 0.
- **Performance Heuristic**:
    - Leverages global `lld` linker for sub-second verification.
    - If incremental check > 3s, notify of bottleneck and check `sccache` status.

## 3. Iron Laws
- **Zero-Tolerance**: No broken Rust code remains in the active workspace.
- **Strictness**: Must run on every save/write to ensure "Ready to Forge" state.
