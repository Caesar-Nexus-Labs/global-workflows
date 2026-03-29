---
name: trigger-task-logger
description: Deep task completion logging and swarm coordination (RE-ENGINEERED).
event: trigger-post-tool
---

# Trigger: Task Logger (`trigger-task-logger`)

## 1. Description
Handles the recording of every successful tool execution into the persistent session log. In "Agent Team Mode," it synchronizes progress across the swarm by injecting completion summaries for the Lead Agent.

## 2. Execution Logic
- **Invoke Event**: `trigger-post-tool`.
- **Payload Capture**: `tool_name`, `tool_input`, `tool_response.exit_code`.
- **Action**:
    1. Append entry to the active journal artifact managed by **[/forge-journal](../commands/forge-journal.md)**.
    2. **Swarm Intelligence**: If 3+ subagents are active, generate a `Swarm-Status` JSON and broadcast to the orchestration engine.
    3. **Transcript Backup**: Save a snapshot of the modified file to `.caesar/checkpoints/` if the tool was `Write` or `Edit`.

## 3. Iron Laws
- **Persistence**: Logs must be written synchronously to avoid data loss on crash.
- **Clarity**: Use ISO v1.1 semantic logging (Timestamp, Agent-Tier, Action-Status).
