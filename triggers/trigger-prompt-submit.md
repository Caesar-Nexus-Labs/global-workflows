# trigger-prompt-submit

> **Pre-LLM Enrichment** — Inject context rules and validate input before LLM processing.

## Metadata

- **Event**: User submits prompt (before LLM receives it)
- **Type**: Context Enrichment
- **SLA**: < 500ms
- **Deterministic**: YES (no LLM, hard rules only)

## Description

Fires when user submits a prompt. Performs:
1. Inject /forge-development-rules.md into context
2. Type-check input (syntax, format validation)
3. Detect command intent early
4. Strip/redact PII if present
5. Validate parameter syntax
6. Output: enriched context or DENY with reason

## Output Format

```json
{
  "trigger_id": "trigger-prompt-submit-20260317-145632",
  "event": "prompt_submit",
  "action": "PERMIT",
  "enriched_context": {
    "rules_injected": 24,
    "pii_stripped": false,
    "syntax_valid": true
  }
}
```

## Failure Handling

- **Invalid syntax**: DENY with error message
- **PII detected**: STRIP and warn user
- **Rule violation**: DEFER to manual review

**Status**: PROD-READY ✅
**Version**: 1.0.0
