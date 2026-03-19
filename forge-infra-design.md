---
name: /forge-infra-design
description: Architecting scalable, secure infrastructure as code (IaC).
category: Operations
status: Stable
methodology: Caesar Nexus Logic
---

# Infrastructure Design (/forge-infra-design)

## Caesar Nexus Execution Logic

### Phase 1: Requirements Mapping
- **Call**: `/forge-brainstorm`
- **Action**: Define load requirements, security zones, and resource limits.

### Phase 2: Planning & Blueprinting
- **Call**: `/forge-plan`
- **Action**: Orchestrate terraform/pulumi modules and redundancy patterns.

### Phase 3: Execution (IaC Implementation)
- **Implement**: Build declarative infrastructure files via `/forge-cook`.

### Phase 4: Security Audit
- **Call**: `/forge-review`
- **Action**: Mandatory check for secrets exposure and networking rules.

### Phase 5: Finalization & Sync
- **Update**: Infrastructure diagrams and internal documentation.

## Iron Laws
- **Declarative Only**: No manual cloud console changes; everything must be documented in code.
- **Secrets Isolation**: Use dedicated secrets manager or KMS providers.
- **Redundancy**: High availability (multi-AZ) is mandatory for production envs.

