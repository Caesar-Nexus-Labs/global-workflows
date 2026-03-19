---
name: /forge-clean
description: Automated code hygiene and dead code removal.
category: Hygiene
status: Stable
methodology: Caesar Nexus Logic
---

# Code Clean & Hygiene Workflow (/forge-clean)

## 1. What This Workflow Does
Automated "Garbage Collection" for the codebase. Removes dead code, unused imports, and stale temporary files.

## 2. Actions
- Runs `cargo sweep` or equivalent.
- Identifies "Zombies" (Functions that are never called).
- Standardizes indentation and newline conventions.
