---
name: /forge-development-rules
description: Global quality standards, architecture patterns, and TDD laws for Caesar Nexus.
category: Core Constitution
status: Stable
methodology: System Standard
---

# Forge Development Rules

## 1. Code Quality Standards
- **Premium Architecture**: Always follow DDD or Clean Architecture patterns.
- **Strict Environment**: TypeScript strict mode, Rust zero-cost abstractions, mandatory linting.
- **Testing**: 100% test coverage for new business logic. Mandatory TDD (RED-GREEN-REFACTOR).
- **Code Comments**: Self-explanatory code is preferred; complex logic must have JSDoc/RustDoc.

## 2. Agent Orchestration Protocol
- **Discovery**: Use Scout agents for initial repo analysis.
- **Planning**: Mandatory `/forge-plan` before any `/forge-cook`.
- **Handoffs**: 
  - `planner` creates `plans/*.md`.
  - `cook` (Fullstack Dev) reads `plans/*.md`.
  - `test` (Tester) validates implementation.
  - `review` (Reviewer) verifies quality gates.

## 3. Implementation Principles
- **Atomic Tasks**: Break work into the smallest possible implementable units.
- **Atomic Commits**: One feature/fix per commit. Conventional Commits enforced.
- **No Hallucinations**: Verify all file paths and tool outputs before proceeding.

## 4. Quality Gates
- **Phase 1 (Agent)**: Self-review and linting.
- **Phase 2 (Lead)**: Compliance check against `forge-development-rules.md`.
- **Phase 3 (Merge)**: Final test pass on CI/Stage. Score ≥ 9.5 required.

## 5. Iron Laws
- **Foundation-First**: No features can be cooked until bootstrap is verified.
- **Pure Caesar**: Zero references to third-party templates.
- **Zero Legany**: Legacy code must be isolated before refactoring.

