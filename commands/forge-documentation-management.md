---
name: /forge-documentation-management
description: Standards for technical and project documentation lifecycle.
category: Core Constitution
status: Stable
methodology: System Standard
---

# Forge Documentation Management

## 1. Documentation Standards
- **Source of Truth**: The `docs/` directory is the single source of truth.
- **Format**: All documentation must be in high-quality Markdown.
- **Architecture**: Always maintain an `architecture_overview.md` with Mermaid diagrams.

## 2. Documentation Lifecycle
- **Trigger**: Every `/forge-cook` must evaluate documentation impact.
- **Sync**: Documentation must be updated *before* or *concurrently* with the PR merge.
- **Master Index**: Update the project's Master Index to reflect new modules.

## 3. Knowledge Retention
- **Journaling**: Daily execution logs must be stored in `.claude/journals/`.
- **Project Logs**: High-level decisions must be logged in `DECISIONS.md`.
- **Brain Integration**: Sync critical context to the Antigravity Brain.

## 4. File Structure
- `docs/api/`: Endpoint definitions.
- `docs/architecture/`: System design and diagrams.
- `docs/guides/`: User and developer manuals.
- `docs/rfc/`: Requests for Comments for major changes.

## 5. Iron Laws
- **Concurrence**: Never ship code without corresponding documentation updates.
- **Diagrams**: Complex logic must be visualized using Mermaid diagrams.
- **Zero Hallucination**: Only document verified behaviors.

