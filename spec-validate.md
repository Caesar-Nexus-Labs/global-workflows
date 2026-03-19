---
name: /spec-validate
description: Validate completeness and technical feasibility of a feature specification.
category: Planning & Architecture
status: Stable
methodology: Caesar Nexus Logic
---

# Specification Validation (/spec-validate)

## 1. Description
Audits a specification to ensure it is technically sound, complete, and free of overengineering before implementation begins.

## 2. Validation Gates
- **Completeness**: Are all edge cases and error states defined?
- **Feasibility**: Can the current tech stack implement the proposed solution?
- **Scope Audit**: Does the spec contain any out-of-scope "gold-plating"?
- **Consistency**: Does it align with existing system architecture?

## 3. Iron Laws
- **Zero Gaps**: Any missing requirement results in a "Fail" verdict.
- **Architect Approval**: Mandatory sign-off for critical infrastructure specs.

