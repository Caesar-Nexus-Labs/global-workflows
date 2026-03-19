---
name: /forge-kit-builder
description: Automated creation of specialized Caesar Nexus Skill Kits.
category: Meta-Automation
status: Stable
methodology: Caesar Nexus Logic
---

# Custom Kit Builder (/forge-kit-builder)

## Caesar Nexus Execution Logic

### Phase 1: Definition & Scoping
- **Action**: Prompt for purpose, target agents, and tier structure.

### Phase 2: Planning & Blueprinting
- **Call**: `/forge-plan`
- **Action**: Define the skill set (10-20 core skills) and interactions.

### Phase 3: Execution (Generation)
- **Call**: `skill-creator`
- **Action**: Simultaneously generate all skills and workflow files.

### Phase 4: Validation
- **Action**: Run `nexus-validate-*` suite against the new kit.

### Phase 5: Distribution
- **Action**: Package to `skills_repo/` and update Master Index.

## Iron Laws
- **Standardized Tiers**: Must follow Management → Dev → Quality → Ops tiering.
- **Zero Orphan**: Every new skill must belong to a defined workflow.
- **Pure Quality**: Custom kits must achieve Score ≥ 9.5.

