---
name: /checkpoint-list
description: List available project checkpoints with timestamps and descriptions.
category: Management
status: Stable
methodology: Git Ops
---

# Checkpoint Registry List (/checkpoint-list)

## 1. Description
Displays the history of project save-points, allowing the user/agent to identify recovery targets.

## 2. Execution Logic
1. **Registry Scan**: Pull all git commits with the `[CHECKPOINT]` prefix.
2. **Journal Fetch**: Cross-reference with the technical journal for detailed descriptions.
3. **Display**: Present a clean list with IDs, timestamps, and change summaries.

## 3. Iron Laws
- **Readability**: Summaries must clearly indicate the purpose of each checkpoint.

