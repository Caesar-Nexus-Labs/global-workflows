# trigger-pre-tool

> **Pre-Execution Security Guardrails** — Validate tool calls before execution.

## Metadata

- **Event**: Before any tool/MCP call execution
- **Type**: Security Gate
- **SLA**: < 200ms per call
- **Deterministic**: YES (whitelist validation)

## Description

Fires before any tool execution. Performs:
1. Whitelist check (only approved MCP tools)
2. Parameter type validation
3. Range checks (no negative values, reasonable counts)
4. Credential/secret parameter check (none in plaintext)
5. Environment variable validation
6. Output: PERMIT / DEFER / DENY with reason

## Whitelist

```yaml
approved_tools:
  - read_file
  - write_file
  - bash_command
  - git_command
  - http_request
  - database_query
```

## Output Format

```json
{
  "trigger_id": "trigger-pre-tool-20260317-145632",
  "tool_name": "bash_command",
  "action": "PERMIT",
  "parameter_checks": {
    "command_safe": true,
    "no_plaintext_secrets": true,
    "valid_ranges": true
  }
}
```

**Status**: PROD-READY ✅
**Version**: 1.0.0
