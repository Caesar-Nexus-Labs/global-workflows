---
name: /market-persona
description: The "Audience DNA Extractor". Identifies the specific end-user profiles, their pain points, and psychological triggers to tailor engineering and marketing efforts.
category: Marketing & Growth
status: Stable
methodology: Caesar Nexus Logic
---

# User Persona Mapping (/market-persona)

## 1. Description
The "Audience DNA Extractor". Identifies the specific end-user profiles, their pain points, and psychological triggers to tailor engineering and marketing efforts.

## 2. Caesar Nexus Execution Loop

### Phase 1: Lead Analysis
1. **Strategic Scouting**: Invoke **[/market-scout-logic](./market-scout-logic.md)** to understand the current audience landscape.
2. **Behavioral Discovery**: Pulse an active **[/market-plan](./market-plan.md)** to see the targeted market segments.

### Phase 2: Persona Archetyping
1. **Pain Point Mapping**: Invoke **[/forge-problem-solving](./forge-problem-solving.md)** to identify the core technical and emotional obstacles for each persona.
2. **Solution Alignment**: Pulse **[/forge-ba](./forge-ba.md)** to ensure the engineering features solve these specific pain points.

### Phase 3: Copy & Messaging Strategy
1. **Hook Generation**: Trigger **[/market-write](./market-write.md)** to create tailored hooks for each persona.
2. **Trigger**: `trigger-market-brand-gate` ensures the persona archetypes align with Caesar Nexus's voice.

### Phase 4: Integration & Handoff
1. **Campaign Link**: Redirect to an active **[/market-campaign](./market-campaign.md)** to apply the persona DNA.
2. **Trigger**: `trigger-task-logger` record's the persona approval.

## 3. Iron Laws
- **Empirical Basis Only**: Personas must be based on real market data or verified competitor personas.
- **Actionable Insight**: Every persona must have at least 3 specific "Triggers" that influence the `/market-write` process.
- **English Standard**: All persona reports and profile cards must be in English.
