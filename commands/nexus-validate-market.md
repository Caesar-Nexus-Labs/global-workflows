---
name: /nexus-validate-market
description: Automated compliance and quality validation for marketing assets and campaigns.
category: Compliance & Audit
status: Stable
methodology: Nexus Protocol
---

# Marketing Compliance Validation (/nexus-validate-market)

## Caesar Nexus Execution Logic

### Phase 1: Artifact Collection
- **Action**: Gather all marketing assets (Copy, Design, Emails, Ad Scripts).
- **Rule**: No un-vetted asset enters the validation pipeline.

### Phase 2: Brand & ISO Check
- **Action**: Verify 100% adherence to Caesar Nexus Brand Identity and Tone of Voice.
- **Action**: Ensure 100% English standardization across all assets.

### Phase 3: Legal & Regulatory Audit
- **Action**: Check for PII leaks, misleading claims, and GDPR/CAN-SPAM compliance.
- **Action**: Verify "Irresistible Offer" transparency.

### Phase 4: Quality Gate (Premium)
- **Action**: Professional aesthetic and "WOW" factor audit (Target Score ≥ 9.5).
- **Action**: Cross-device responsiveness check.

### Phase 5: Verdict & Remediation
- **Action**: Outcome: Approved or Remediation Required via `/nexus-remediate`.
- **Log**: Save validation report to `reports/nexus-validate-*.md`.

## Iron Laws
- **Zero Tolerance**: One compliance failure halts the entire campaign launch.
- **Traceability**: Every validation verdict must link to a specific rule in the Compliance Kit.
- **Impartiality**: Validation must be performed by a Nexus-authorized agent, independent of the Campaign creators.

