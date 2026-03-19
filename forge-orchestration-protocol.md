---
name: /forge-orchestration-protocol
description: Communication and task-sharing standards between multiple agents.
category: Core Constitution
status: Stable
methodology: System Standard
---

# Forge Orchestration Protocol

## 1. Orchestration Modes
### Sequential (Default Trace)
- **Flow**: `planner` → `developer` → `tester` → `reviewer` → `git_manager`.
- **Use Case**: Linear feature development and bug fixes.
- **Logic**: Each agent builds on the 100% verified output of the previous agent.

### Parallel (Speed Burst)
- **Flow**: Multiple `scout` or `researcher` agents running simultaneously.
- **Use Case**: Large codebase analysis or multi-platform research.
- **Gate**: Results must be synthesized by a `planner` agent before continuation.

### Hybrid (The Caesar Nexus)
- **Flow**: Parallel discovery nested within a sequential implementation loop.

## 2. Handoff Protocols
每一Handoff must satisfy the **Zero-Ambiguity Rule**:
1. **Artifact Exchange**: All handoffs must be documented in `reports/` or `plans/`.
2. **State Verification**: Receiving agent must verify input integrity before starting.
3. **Checkpoint Logs**: Status must be updated in active `plan.md`.

## 3. Conflict Resolution
- **Rule 1**: The `planner` agent is the final authority on implementation logic.
- **Rule 2**: The `reviewer` agent is the final authority on code quality and security.
- **Rule 3**: Stalemate triggers User (Lead Architect) notification.

## 4. Fail-Safe Recovery
- If an agent fails, task reverts to previous stable checkpoint.
- The `debugger` agent is triggered to analyze orchestration failure.
- Auto-cleanup of all orphan files or aborted branches.

## 5. Iron Laws
- **ISO Standard**: All internal log messages and code comments must be in English.
- **Zero Orphan**: Every file must belong to a defined module.
- **Persistence**: Blueprint progress must be saved at every phase.

