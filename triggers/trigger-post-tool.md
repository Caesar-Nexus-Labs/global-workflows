# trigger-post-tool

> **Post-Execution Logging & Validation** — Audit outputs and verify schema compliance.

## Metadata

- **Event**: After tool/MCP call completes
- **Type**: Audit & Quality Gate
- **SLA**: < 300ms per call
- **Deterministic**: YES (schema validation)

## Description

Fires after any tool execution. Performs:
1. Log output to audit trail (immutable)
2. Type-validate output matches schema
3. Strip sensitive data from logs
4. Trigger /forge-task-logger on completion
5. Flag anomalies (unexpected output, errors)
6. Output: audit record

## Output Format

```json
{
  "trigger_id": "trigger-post-tool-20260317-145632",
  "tool_name": "bash_command",
  "status": "success",
  "output_valid": true,
  "schema_match": true,
  "sensitive_data_stripped": false,
  "audit_logged": true
}
```

## Sensitive Data Patterns

- AWS keys, API tokens → STRIPPED
- Passwords, private keys → STRIPPED
- Database connection strings → REDACTED
- Personal info (emails, IPs) → REDACTED

**Status**: PROD-READY ✅
**Version**: 1.0.0
