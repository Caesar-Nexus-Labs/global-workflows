---
name: /forge-review
description: 6-agent parallel code review for architecture, security, performance, best practices, testing, and docs.
category: Quality & Review
status: Stable
methodology: Caesar Nexus Logic
agent_id: agent.reviewer_agent
primary_hub: cn:c12_audit
primary_workflow: cn:c70_comprehensive_review
---

# Parallel Code Review (/forge-review)

## 1. Description
A high-intensity, 6-agent parallel review process designed to audit every dimension of a code change simultaneously. This is the "Gold Standard" for production-ready code.

## 2. Canonical Agent Chain

- **Conductor Persona**: `agent.reviewer_agent`
- **Process Hub**: `cn:c12_audit`
- **Primary Workflow**: `cn:c70_comprehensive_review`
- **Execution Contract**: read-only audit with explicit remediation handoff
- **Handoff**: `/nexus-remediate` or `/forge-execute-plan` after review acceptance

## 3. Review Ensemble (6 Agents)
1. **Architecture Reviewer**: Audits structural integrity, patterns, and C4 alignment.
2. **Security Reviewer**: Scans for vulnerabilities, secrets exposure, and PII leaks.
3. **Performance Reviewer**: Identifies bottlenecks, memory leaks, and inefficient allocations.
4. **Best Practices Reviewer**: Ensures adherence to `forge-development-rules.md` and naming conventions.
5. **Testing Reviewer**: Audits test coverage, TDD logic, and edge-case verification.
6. **Documentation Reviewer**: Ensures code documentation and Master Index parity.

## 4. Caesar Nexus Execution Loop
1. **Ensemble Trigger**: All 6 reviewers are spawned in parallel with the same context.
2. **Adversarial Audit**: Agents perform deep inspections and log findings separately.
3. **Collision Detection**: The `reviewer-lead` synthesizes findings and identifies conflicting or critical issues.
4. **Verdict Generation**: High-fidelity report issued with a consolidated quality score.
5. **Remediation**: If Score < 9.5, trigger `/forge-refactor` or `/nexus-remediate`.

## 5. Iron Laws
- **Strict Gating**: No PR shall be merged without a green `/forge-review` report.
- **Independence**: Reviewers must not have participated in the implementation phase.
- **Zero Criticals**: Any "Critical" or "Major" security/arch issue results in an immediate halt.

