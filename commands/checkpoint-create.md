---
name: /checkpoint-create
description: Save project snapshot for safe experimentation and rollback.
category: Management
status: Stable
methodology: Git Ops
---

# State Checkpoint Creation (/checkpoint-create)

## 1. Description
Manual or automatic capture of the current project state (Git snapshot + session context) to provide a safety net for experimentation.

## 2. Execution Logic
1. **Context Capture**: Save current agent task status and session environment.
2. **Git Snapshot**: Execute a temporary git commit or stash with the prefix `[CHECKPOINT]`.
3. **Registry Update**: Log the checkpoint ID, timestamp, and description in the project journal.

## 3. Iron Laws
- **Sanity Check**: Never create a checkpoint if the system is in a corrupted state (unless for debugging).
- **Efficiency**: Checkpoints are lightweight; do not include non-essential artifacts.
- **Persistence**: Checkpoints must survive session restarts.

