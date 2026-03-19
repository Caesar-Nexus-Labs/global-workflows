---
name: "forge:ba"
description: "Business Analyst agent. Deeply understands user requirements before any planning or coding begins."
category: "c15_strategy"
status: "verified"
methodology: "methodology"
---

# Business Analysis Workflow (/forge-ba)

## 1. Description
The "Requirement Translator". Bridges the gap between vague user intent and hard technical requirements. It is the filter for all upstream specifications.

## 2. Caesar Nexus Execution Loop

### Phase 1: Intent Extraction
1. **Deep Elicitation**: Analyze the user prompt for hidden goals and MVP boundaries.
2. **Context Pulse**: Pulse **[/forge-scout](./forge-scout.md)** to see if the feature already exists or conflicts.
3. **Trigger**: `trigger-rules-reminder` ensures business logic follows the Caesar Nexus growth mindset.

### Phase 2: User Persona Mapping
1. **Persona Discovery**: Invoke **[/market-persona](./market-persona.md)** to identify who this feature is for.
2. **User Journey**: Pulse **[/market-funnel](./market-funnel.md)** to see where this feature fits in the funnel.

### Phase 3: Constraint & Logic Modeling
1. **Paradox Detection**: Invoke **[/forge-problem-solving](./forge-problem-solving.md)** to find conflicting business requirements.
2. **Technical Feasibility**: Trigger **[/forge-research](./forge-research.md)** for any novel business calculations.

### Phase 4: Spec Bridge & Handoff
1. **Specification Link**: Redirect to **[/spec-create](./spec-create.md)** to formalize the business requirements.
2. **Trigger**: `trigger-task-logger` records the business sign-off.

## 3. Iron Laws
- **No Vague Logic**: Any business requirement that cannot be translated into a "Test" is a failure.
- **Traceability**: Every feature must solve a specific problem for a specific Persona.
- **English Standard**: All BA reports and requirement lists must be in English.
tions, **ONE AT A TIME**:
1. **WHO**: Who is the end user? What's their technical level?
2. **WHAT**: What specific outcome do they need? What does "done" look like?
3. **WHY**: Why do they need this? What problem does this solve?
4. **BOUNDARIES**: What should this NOT do? What is out of scope?
### Step 3: Hidden Requirement Discovery
Analyze for:
- Auth/Authz, Rate limiting, Persistence (DB schema).
- Error handling, Offline behavior, Accessibility.
- GDPR/Compliance, Analytics tracking.

### Step 4: Scope Definition
Produce a report covering:
- **In-Scope**: Explicit features.
- **Out-of-Scope**: Explicit exclusions.
- **Assumptions**: Critical risks if wrong.
- **Dependencies**: APIs, services, access required.

### Step 5: User Stories & Acceptance Criteria
Format: `As a [persona], I want to [action] so that [benefit]`.
- Every story must have at least 2 **Acceptance Criteria** (Happy Path + Error Case).
- Criteria must be **TESTABLE** (for Phase 13 TDD).

### Step 6: Requirements Document
Save to `.caesar/features/<name>/requirements.md`.
→ Hand off to `/forge-plan`.

