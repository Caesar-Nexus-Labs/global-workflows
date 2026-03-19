---
name: /forge-refactor
description: Proactive improvement of code structure, maintainability, and performance without changing behavior.
category: Code Quality
status: Stable
methodology: Caesar Nexus Logic
---

# Code Refactoring (/forge-refactor)

## 1. Description
Proactive improvement of code structure, maintainability, and performance without changing external behavior.

## 2. Trigger Events
- **Code Review**: Quality score < 9.5.
- **Technical Debt**: Identified smells or outdated patterns.
- **Performance**: Profiling reveals bottlenecks.

## 3. Caesar Nexus Refactoring Flow
1. **Safety Net**: Ensure 100% test coverage for the target area. **GATE**: No refactor without tests.
2. **Plan Target**: Trigger `/forge-plan` to map the transformation.
3. **Execution**: Implement changes using the TDD Green-Refactor cycle.
4. **Verification**: Run all tests; benchmarking if performance was the goal.
5. **Review**: Mandatory `/forge-review` by an independent agent.

## 4. Iron Laws
- **Behavior Preservation**: Refactoring *must not* change functional outcomes.
- **Atomic Transformation**: Refactor in small, verifiable steps.
- **Documentation Sync**: Update all affected docs and diagrams immediately.

