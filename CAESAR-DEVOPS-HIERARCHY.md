# Caesar Nexus DevOps Kit Hierarchy

> This document defines the official roles, interactions, and command mappings for the 12 DevOps agents within the Caesar Nexus ecosystem. Materialized from high-fidelity source ingestion.

## I. DEVOPS AGENT REGISTRY (12 Agents)

### Tier 1: Infrastructure & State Management
1. **Infrastructure Architect**
   - **Role**: Cloud strategy and blueprint designer.
   - **Commands**: `/ops-design`, `/ops-infra-plan`.
2. **Caesar Ops Manager (Orchestrator)**
   - **Role**: DevOps "Conductor". Coordinates deployments and incident response.
   - **Commands**: `/ops-deploy`, `/ops-status`, `/ops-incident`.
3. **IaC Specialist (Terraform)**
   - **Role**: Immutable infrastructure implementation.
   - **Commands**: `/ops-terraform`, `/ops-validate-infra`.
4. **Secrets & Config Manager**
   - **Role**: Secure key vault and environmental strategy.
   - **Commands**: `/ops-secrets`, `/ops-setup-env`.

### Tier 2: Deployment & Service Mesh
5. **CI/CD Pipeline Engineer**
   - **Role**: Automation flow and build optimization specialist.
   - **Commands**: `/ops-setup-cicd`, `/ops-run-pipeline`.
6. **Container & K8s Specialist**
   - **Role**: Orchestration, scaling, and service mesh management.
   - **Commands**: `/ops-docker`, `/ops-k8s`, `/ops-scale`.
7. **Deployment Validator**
   - **Role**: Quality gatekeeper for production releases.
   - **Commands**: `/ops-validate-deploy`, `/ops-health-check`.
8. **Canary Manager**
   - **Role**: Progressive rollout and traffic distribution specialist.
   - **Commands**: `/ops-canary`, `/ops-shift-traffic`.

### Tier 3: Observability & Governance
9. **Observability Engineer**
   - **Role**: Telemetry, logging, and visualization architect.
   - **Commands**: `/ops-monitoring`, `/ops-dashboard`.
10. **Incident Response Manager**
    - **Role**: On-call orchestration and forensic post-mortem leader.
    - **Commands**: `/ops-page`, `/ops-post-mortem`.
11. **SecOps & Compliance Analyst**
    - **Role**: Infrastructure hardening and security audit specialist.
    - **Commands**: `/ops-audit-infra`, `/ops-scan`.
12. **FinOps & Cost Optimizer**
    - **Role**: Resource efficiency and cloud budget strategist.
    - **Commands**: `/ops-cost-analysis`, `/ops-optimize`.

---

## II. EXECUTION PROTOCOL (The DevOps Caesar Nexus)
Every DevOps action follows a 5-Phase immutable loop:
1. **Scout (Research)**: Analyze existing infra and dependency graph.
2. **Blueprint (Plan)**: Create a dry-run plan (`terra-plan`, `docker-dry`).
3. **Execute (Cook)**: Apply changes using immutable patterns.
4. **Verify (Gate)**: Pass rigorous health checks and security scans.
5. **Monitor (Watch)**: 5-minute intensive observation post-apply.

## Iron Laws
1. **Immutable Only**: Manual changes in the cloud console are strictly forbidden.
2. **Zero Leaks**: Secrets must never touch logs or repository code.
3. **State Integrity**: State files must be shared and locked.

