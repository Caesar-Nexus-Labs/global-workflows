---
name: /spec-decompose
description: Break specification into small, implementable, and self-contained tasks.
category: Planning & Architecture
status: Stable
methodology: Caesar Nexus Logic
---

# Specification Decomposition (/spec-decompose)

## 1. Description
Transforms a high-level technical specification into a granular list of atomic development tasks for parallel or sequential execution.

## 2. Execution Logic
1. **Dependency Analysis**: Identify the order of implementation (Data Layer → Logic → API → UI).
2. **Atomic Breakdown**: Define tasks that take < 4 hours each and are verifiable.
3. **Parallel Mapping**: Identify tasks that can be executed concurrently by multiple agents.
4. **Task Hydration**: Inject TDD requirements and validation gates into each task definition.

## 3. Iron Laws
- **Self-Contained**: Every task must contain all necessary information for execution.
- **Verifiable**: Every task must have a corresponding test case.

