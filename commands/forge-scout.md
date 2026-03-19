---
name: /forge-scout
description: Discovery and analysis of codebase structure, patterns, and dependencies.
category: Research & Discovery
status: Stable
methodology: Caesar Nexus Logic
---

# Codebase Scouting (/forge-scout)

# Codebase Scouting (/forge-scout)

## 1. Description
Discovery and analysis of codebase structure, patterns, and dependencies. It is the "Intelligence Agent" that provides technical context for planning and implementation.

## 2. Caesar Nexus Execution Loop

### Phase 1: Structural Reconnaissance
1. **Entry Point Discovery**: Locate the main application and library entry points.
2. **Dependency Mapping**: Map internal module dependencies and external crate/npm packages.
3. **Symbol Extraction**: Invoke **[/forge-gkg](./forge-gkg.md)** to extract key symbol relationships.

### Phase 2: Pattern & Logic Analysis
1. **Design Pattern Recognition**: Identify established design patterns (e.g., Factory, Repository, Middleware).
2. **Knowledge Discovery**: Invoke **[/forge-research](./forge-research.md)** for any foreign libraries or patterns found.
3. **Complexity Audit**: Trigger `trigger-edit-tracker` to identify potential logic bottlenecks.

### Phase 3: Integration & Dependency Check
1. **MCP Scoping**: If MCP related, invoke **[/forge-mcp-management](./forge-mcp-management.md)** to check tool compatibility.
2. **Infrastructure Alignment**: Pulse **[/ops-infra-plan](./ops-infra-plan.md)** for infra-level constraints.

### Phase 4: Intelligence Output & Handoff
1. **Report Generation**: Output `reports/scout-*.md` with visualizations and module summaries.
2. **Planning Bridge**: Redirect to **[/forge-plan](./forge-plan.md)** with the gathered context.
3. **Trigger**: `trigger-task-logger` records the scouting findings.

## 3. Iron Laws
- **Zero Hallucination**: Report only what exists; do not assume undocumented or skeletal logic.
- **Traceability**: All scout findings must link back to specific file and line numbers.
- **Context Retention**: Scouted context must be preserved for the entire duration of the linked `/forge-plan`.

