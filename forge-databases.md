---
name: /forge-databases
description: Comprehensive lifecycle management for SQL/NoSQL databases.
category: Operations
status: Stable
methodology: Caesar Nexus Logic
---

# Database Management (/forge-databases)

## Caesar Nexus Execution Logic

### Phase 1: Storage Strategy
- **Call**: `/forge-brainstorm`
- **Action**: Choose engine (PostgreSQL, MongoDB, Pinecone) and define indexing strategy.

### Phase 2: Planning & Schema
- **Call**: `/forge-plan`
- **Action**: Orchestrate tables, relationships, and constraints.

### Phase 3: Execution (Provisioning)
- **Call**: `/forge-cook`
- **Action**: Build database instances and initial schema scripts.

### Phase 4: Migration & Seed
- **Call**: `/forge-db-migration`
- **Action**: Execute versioned migrations and populate initial seed data.

### Phase 5: Audit & Security
- **Call**: `/forge-review`
- **Action**: Audit connection strings security and performance optimization.

## Iron Laws
- **Persistence First**: Ensure WAL (Write-Ahead Logging) or equivalent is enabled.
- **Access Control**: Mandatory SSL/TLS for all connections.
- **Secrets Isolation**: Connection strings must be stored in encrypted environment variables.

