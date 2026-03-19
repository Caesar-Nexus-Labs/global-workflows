---
name: Building REST & GraphQL APIs
description: End-to-end design and implementation of highly scalable, secure, and documented APIs.
category: Code Development
status: Stable
methodology: Caesar Nexus Logic
---

# Building REST & GraphQL APIs (/forge-api)

## Caesar Nexus Execution Logic

### Phase 1: Interface Design
- **Call**: `/forge-brainstorm`
- **Action**: Define endpoints, data models, and authentication requirements.

### Phase 2: Planning & Schema
- **Call**: `/forge-plan`
- **Action**: Implement database migrations using `/forge-databases`.

### Phase 3: Execution (TDD Red-Green-Refactor)
- **RED**: Write integration tests for defined endpoints.
- **GREEN**: Trigger `/forge-cook` to build routes, controllers, and services.
- **REFACTOR**: Optimize for performance and scalability.

### Phase 4: Security & Docs
- **Security**: Apply `better-auth` middleware and rate-limiting.
- **Docs**: Trigger `/forge-docs` to generate Swagger/OpenAPI references.

### Phase 5: Finalization
- **Verify**: Request/Response must match defined schemas.
- **Merge**: Safe commit to development branch.

## Iron Laws
- **Contract First**: Define the API signature before writing implementation logic.
- **Versioning**: All APIs must be versioned from day one (v1, v2).
- **Graceful Errors**: Standardized error response formats across the entire system.

