---
name: /checkpoint-restore
description: Restore project to a previous state from a saved checkpoint.
category: Management
status: Stable
methodology: Git Ops
---

# State Restoration (/checkpoint-restore)

## 1. Description
Resets the project to a specific checkpoint, undoing any recent changes or failed experiments while maintaining history integrity.

## 2. Execution Logic
1. **Identification**: Locate the target checkpoint ID or timestamp.
2. **Safety Check**: Verify the current state and offer a "Pre-restore Checkpoint" for safety.
3. **State Reset**: Perform git checkout/reset to the checkpoint commit.
4. **Context Recovery**: Restore agent task state and environmental parameters.

## 3. Iron Laws
- **No Data Loss**: Always provide a way to undo a restore operation.
- **Traceability**: Log the restore event in the project journal.

