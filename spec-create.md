# /spec-create

> **Technical Specification Generation** — Convert high-level blueprints into detailed specs.

## Metadata

- **Slug**: /spec-create
- **Type**: Specification
- **Agents**: Spec Writer, Technical Lead, Architect
- **Prerequisites**: /forge-plan (blueprint required)
- **Output**: Complete technical specification document

## Description

Transforms /forge-plan output into detailed technical specification with:
- System architecture & components
- Data models & schemas
- API specifications
- User workflows & acceptance criteria
- Error handling & edge cases
- Security & compliance requirements
- Performance requirements
- Deployment considerations

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --blueprint | file | Output from /forge-plan |
| --detail-level | string | technical, business, hybrid |
| --include-examples | boolean | Include code examples & diagrams |
| --format | string | markdown, html, confluence |

## Output

```json
{
  "spec_id": "spec-feature-auth-20260317",
  "feature": "Authentication System v2",
  "sections": 12,
  "components": 8,
  "acceptance_criteria": 24,
  "estimated_dev_days": 12,
  "status": "ready_for_review"
}
```

## Related

- Requires: /forge-plan
- Used by: /spec-decompose, /spec-validate, /spec-execute

**Status**: PROD-READY ✅
**Version**: 1.0.0
