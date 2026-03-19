---
name: /forge-db-migration
description: Safe, versioned schema transformations for Caesar Nexus.
category: Operations
status: Stable
methodology: Caesar Nexus Logic
---

# Database Migration (/forge-db-migration)

## Caesar Nexus Execution Logic

### Phase 1: Impact Analysis
- **Call**: `/forge-scout`
- **Action**: Identify current schema and downstream dependencies.

### Phase 2: Design & Strategy
- **Call**: `/forge-plan`
- **Action**: Orchestrate Step-up/Step-down logic and data preservation.

### Phase 3: Execution (Implementation)
- **Implement**: Create migration scripts using industry standard tools (Diesel, Prisma, or Flyway).

### Phase 4: Validation (Dry Run)
- **Call**: `/forge-test`
- **Action**: Execute migration in a sandbox environment and verify data integrity.

### Phase 5: Handoff & Recording
- **Update**: Schema documentation and project lifecycle logs.

## Iron Laws
- **Zero Data Loss**: Always backup before executing migration in production.
- **Idempotency**: Migrations must be safely re-runnable or reversible.
- **Zero Downtime**: Prioritize expandable schemas (Add before Drop).

