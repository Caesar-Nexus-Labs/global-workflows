---
name: /nexus-risk
description: Identification, assessment, and management of technical and business risks.
category: Compliance & Audit
status: Stable
methodology: Nexus Protocol
---

# Risk Management (/nexus-risk)

## Caesar Nexus Execution Logic

### Phase 1: Detection & Scanning
- **Call**: `/forge-scout --deep`
- **Action**: Identify vulnerabilities, logic flaws, and non-compliance points.

### Phase 2: Assessment & Scoring
- **Action**: Calculate Risk Score (Likelihood x Impact).
- **Goal**: Prioritize risks into Critical, High, Medium, Low.

### Phase 3: Mitigation Strategy
- **Call**: `/forge-plan`
- **Action**: Orchestrate mitigation tasks (Block, Fix, or Accept).

### Phase 4: Verification
- **Call**: `/nexus-audit`
- **Action**: Verify mitigation effectiveness.

### Phase 5: Risk Registry Update
- **Action**: Log status in the Caesar Nexus Central Risk Registry.
- **Update**: Stakeholder alerts if risk remains High.

## Iron Laws
- **Persistence**: Risks remain "Open" until formally remediated or accepted.
- **Honesty First**: Never downplay a verified technical vulnerability.
- **Continuous Monitoring**: High-risk areas must be audited weekly.

