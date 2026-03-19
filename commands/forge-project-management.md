---
name: /forge-project-management
description: Timeline, budget, and resource orchestration.
category: Management
status: Stable
methodology: Caesar Nexus Logic
---

# Project Management Workflow (/forge-project-management)

## 1. What This Workflow Does
Tracks timeline, budget (API costs), and resource allocation across the 70-agent swarm. It ensures no task is abandoned and blockers are escalated.

## 2. Command Syntax
```bash
/forge-project-management [audit|status|escalate]
```

## 3. Action Steps
1. **Audit**: Scans `forge-journal.md` and `task.md` for stale tasks (> 2 hours no update).
2. **Status**: Generates a high-level milestone report for the Architect.
3. **Escalate**: Identifies "Red" tasks that are failing quality gates repeatedly.

## 4. Handoff
- Updates `CAESAR-CENTRAL-HUB.md` status metrics.
