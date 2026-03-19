---
name: /spec-execute
description: Launch multi-agent implementation from a decomposed specification.
category: Planning & Architecture
status: Stable
methodology: Caesar Nexus Logic
---

# Specification Execution Conductor (/spec-execute)

## 1. Description
The main conductor that spawns worker agents to implement the tasks defined in the decomposed specification.

## 2. Execution Logic
1. **Ensemble Spawning**: Initialize specialized agents (Developer, Tester, Reviewer) based on task needs.
2. **Orchestration**: Direct agents through the `/forge-cook` loop for each task.
3. **Progress Sync**: Update the project dashboard and plan status in real-time.
4. **Final Integration**: Invoke `/forge-review` for the entire feature set upon completion.

## 3. Iron Laws
- **Sequential Guard**: Ensure core dependencies are implemented before starting dependent features.
- **Quality Consistency**: Every atomic part must achieve a quality score ≥ 9.5.

