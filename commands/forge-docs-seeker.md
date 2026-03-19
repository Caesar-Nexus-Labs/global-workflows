---
name: /forge-docs-seeker
description: Automated crawler for up-to-date API documentation.
category: Documentation
status: Stable
methodology: Caesar Nexus Logic
---

# Docs Seeker Workflow (/forge-docs-seeker)

## 1. Description
Automated crawler for official documentation. Prevents "guessing" API signatures by retrieving real-time technical truth.

## 2. Caesar Nexus Execution Loop

### Phase 1: Target Isolation
1. **Registry Scouting**: Locate the target crate, npm package, or API on official registries (docs.rs, etc.).
2. **Requirement Sync**: Pulse an active **[/forge-research](./forge-research.md)** session to understand the specific traits/functions needed.

### Phase 2: Deep Crawling
1. **Semantic Search**: Crawl for struct definitions, trait implementations, and usage examples.
2. **Constraint Check**: Identify deprecated methods or breaking changes in recent versions.

### Phase 3: Extraction & Mapping
1. **Trait Mapping**: Map the discovered functions to the project's internal data models.
2. **Trigger**: `trigger-rules-reminder` ensures the discovered API usage follows Caesar Nexus high-speed Rust standards.

### Phase 4: Knowledge Persistence
1. **Master Index Link**: Invoke **[/forge-docs](./forge-docs.md)** to ingest the new API knowledge into the project’s local brain.
2. **Trigger**: `trigger-task-logger` records the successful documentation crawl.

## 3. Iron Laws
- **Source of Truth**: Never use LLM internal "memory" for API signatures if a crawler is available.
- **Zero Ambiguity**: Extracted docs must be formatted for direct AI-agent consumption (Clear Markdown).
- **English Standard**: All technical documentation summaries must be in English.
