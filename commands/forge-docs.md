---
name: /forge-docs
description: Continuous management of technical and project documentation.
category: Management & Docs
status: Stable
methodology: Caesar Nexus Logic
---

# Documentation Workflow (/forge-docs)

## Caesar Nexus Execution Logic

### Phase 1: Audit & Context
- **Call**: `/forge-scout`
- **Action**: Scan `docs/` and gather codebase context via `repomix`.

### Phase 2: Design & Planning
- **Call**: `/forge-plan`
- **Action**: Define documentation needs based on the Architect's guide.

### Phase 3: Execution (Generation)
- **Implement**: Create/update READMEs, setup guides, and architectural overviews.
- **Auto**: Automatically generate OpenAPI/RustDoc from source.

### Phase 4: Verification
- **Audit**: Verify that docs match implementation 1:1.
- **Review**: Professional tone and clarity check.

### Phase 5: Distribution & Finalization
- **Sync**: Update Master Index and project references.
- **Commit**: Final documentation push.

## Iron Laws
- **Concurrence**: Never ship code without corresponding documentation updates.
- **Diagrams**: Complex logic must be visualized using Mermaid diagrams.
- **Zero Hallucination**: Only document verified behaviors.

