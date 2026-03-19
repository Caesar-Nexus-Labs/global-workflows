---
name: trigger-scout-block
description: Prevents reconnaissance and aimless directory exploration.
event: trigger-pre-tool
methodology: Caesar Nexus Logic
---

# Trigger: Scout Block (`trigger-scout-block`)

## 1. Description
A security and efficiency trigger that intercept tool calls (Bash, Glob, Grep, Read) to prevent aimless "scouting" operations. It forces agents to have a clear intent (Plan-first) before accessing the filesystem.

## 2. Trigger Logic
- **Invoke Event**: `trigger-pre-tool`.
- **Matchers**: `Bash`, `Glob`, `Grep`, `Read`.
- **Block Conditions**:
    1. Recursive scans without a specific target file (e.g., `find . -name "*"`).
    2. Overlapping `grep` searches in high-level directories.
    3. Accessing sensitive system files (`.env`, `.git/config`, etc.).
- **Response**: Exit Code 2 (Feedback to LLM: "Denied: Use a targeted scan or consult /forge-plan first").

## 3. Iron Laws
- **Focus**: Every tool call must be preceded by a "Scout intent" or "Plan adherence" check.
- **Efficiency**: Blocks operations that would result in > 10,000 characters of output.
- **Privacy**: Automated masking of any discovered PII or credentials during read operations.
