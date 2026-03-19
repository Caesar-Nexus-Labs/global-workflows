---
name: trigger-market-content-val
description: Brand, SEO, and quality validation for marketing content.
event: trigger-post-tool
matcher: "/market-content|/market-write"
logic_source: claudekit-mkt Content Validation
---

# Trigger: Content Validation (`trigger-market-content-val`)

## 1. Description (Ruột Claudekit Strategy)
A comprehensive quality gate for content production. It enforces Caesar Nexus branding, performs a technical SEO check, and ensures the "Hook-Value-CTA" structure is present and optimized.

## 2. Execution Logic
- **Invoke Event**: `trigger-post-tool`.
- **Action**:
    1. **Brand Audit**: Scan for `claudekit` or `Superpower` legacy keywords.
    2. **SEO Audit**: Run keyword density and meta-tag verification via `/market-seo`.
    3. **Conversion Audit**: Identify the CTA (Call to Action) and verify the tracking link integrity.
- **Logic**: If any check fails, downgrade the content status to `DRAFT-PENDING-FIX` and notify the `Campaign Manager`.

## 3. Iron Laws
- **Purity**: Zero claudekit/external DNA in the final export.
- **premium**: Aesthetics and tone must align with "Caesar Nexus Premium" standards.
