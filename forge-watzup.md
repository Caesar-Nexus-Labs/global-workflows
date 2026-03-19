---
name: /forge-watzup
description: Real-time status report of project progress, milestones, and blockers.
category: Management
status: Stable
methodology: Project Management
---

# Project Status Report (/forge-watzup)

## 1. Description
Provides an instant, high-fidelity summary of the current project state, comparing actual progress against the approved `/forge-plan`.

## 2. Execution Logic
1. **Task Audit**: Scan `plans/` and `task.md` for checked vs. unchecked items.
2. **Milestone Tracking**: Calculate percentage completion for the current phase.
3. **Blocker Detection**: Identify stalled tasks or dependency failures.
4. **Metric Aggregation**: Pull recent test pass rates and quality scores.
5. **Reporting**: Deliver a concise summary of "Where we are" and "What's next".

## 3. Iron Laws
- **Honesty First**: Report blockers and delays immediately; no sugar-coating.
- **Plan Alignment**: Status must always be referenced against the active implementation plan.
- **Actionable**: Every "Blocker" must have an identified remediation owner or task.

