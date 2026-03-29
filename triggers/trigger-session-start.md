---
name: trigger-session-start
description: Global environment initialization and context priming (RE-ENGINEERED).
event: trigger-session-start
---

# Trigger: Session Start (`trigger-session-start`)

## 1. Description
The genesis trigger for every Caesar Nexus session. It handles environment setup, loads the master context, and primes the agents with project-specific constraints.

## 2. Execution Logic
- **Initial Load**:
    1. Load `CAESAR-AGENTS-HIERARCHY.md` and `CAESAR-SLASH-COMMANDS.md`.
    2. Check environment variables (RUST_WRAPPER, SCCACHE, etc.).
- **Maintenance Checks**:
    1. Verify `caesar-builder` synchronization.
    2. Audit the installed command and trigger catalog for integrity.
- **Agent Priming**:
    1. Inject "Project Persona" (e.g., "You are working on a High-Fidelity Rust Monorepo").
    2. Load latest `forge-journal.md` entries for context continuity.

## 3. Iron Laws
- **Speed**: Must complete in < 2 seconds.
- **Fail-Fast**: If critical dependencies are missing, stop session and report error to user.
