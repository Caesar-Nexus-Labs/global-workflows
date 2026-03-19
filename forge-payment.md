---
name: Payment Integration
description: Streamlined integration of payment providers (Stripe, LemonSqueezy).
category: Financial & Integrations
status: Stable
methodology: Caesar Nexus Logic
---

# Payment Integration (/forge-payment)

## Caesar Nexus Execution Logic

### Phase 1: Strategy & Compliance
- **Action**: Choose provider. Verify PCI requirements.

### Phase 2: Flow Planning
- **Call**: `/forge-plan`
- **Action**: Define transaction flow and webhook security.

### Phase 3: Execution (Implementation)
- **Implement**: SDKs, secure idempotent webhooks via `/forge-cook`.

### Phase 4: Verification (Sandbox)
- **Call**: `/forge-test`
- **Action**: Mandatory sandbox bypass for all edge cases.

### Phase 5: Finalization & Handoff
- **Agent**: `compliance-agent` audit. Update docs.

## Iron Laws
- **PCI DSS**: Never handle raw card data.
- **Webhook Check**: Mandatory signature verification.
- **Idempotency**: Ensure zero double-charges.

