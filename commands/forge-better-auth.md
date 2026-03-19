---
name: Secure Authentication
description: Enterprise-grade auth systems following Better-Auth standards.
category: Integrations & Specialized
status: Stable
methodology: Caesar Nexus Logic
---

# Secure Authentication (/forge-better-auth)

## Caesar Nexus Execution Logic

### Phase 1: Security Strategy
- **Call**: `/forge-brainstorm`
- **Action**: Focus on threat modeling and data sensitivity.

### Phase 2: Provider Planning
- **Call**: `/forge-plan`
- **Action**: Configure OAuth providers or local database adapters.

### Phase 3: Execution (TDD Red-Green-Refactor)
- **TDD**: Write failing security tests for tokens and sessions.
- **Inject**: Implement strict auth (RBAC/ABAC) guards via `/forge-cook`.

### Phase 4: UI & Audit
- **Frontend**: Generate premium, secure login/register interfaces.
- **Audit**: Mandatory `/forge-review` for token security.

### Phase 5: Finalization
- **Verify**: Edge case testing (empty tokens, expired sessions).
- **Confirm**: Adherence to GDPR/SOC2 standards.

## Iron Laws
- **Secrets Management**: Never store API keys or secrets in code.
- **Zero Trust**: Always assume unauthorized access attempts.
- **Compliance**: Adhere to global data handling standards.

