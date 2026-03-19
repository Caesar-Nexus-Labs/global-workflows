---
name: trigger-edit-tracker
description: Tracks complexity accumulation and triggers refactoring alerts.
event: trigger-post-tool
methodology: Caesar Nexus Logic
---

# Trigger: Edit Tracker (`trigger-edit-tracker`)

## 1. Description
Monitors the number of consecutive edits to a single file or module. When a complexity threshold is reached, it automatically recommends a refactoring session to maintain "Zero-Cost Abstraction" and "Clean Code" standards.

## 2. Trigger Logic
- **Invoke Event**: `trigger-post-tool`.
- **Matchers**: `Edit`, `Write`, `MultiEdit`.
- **Counter**: Maintain an internal `edit_count` per session.
- **Threshold**: 5 consecutive edits.
- **Action at Threshold**:
    - Inject Message: "⚠️ Complexity Warning: You have made [N] edits. To ensure Caesar Nexus quality (≤ 20 lines per function), consider invoking `/forge-refactor` or `/forge-clean`."
- **Reset**: Reset counter after a `/forge-review` or successful test pass.

## 3. Strategic Alignment
- **Goal**: Prevent "Franken-code" and ensure long-term maintainability.
- **Constraint**: Must not block the user, only provide high-fidelity suggestions to the agent.
