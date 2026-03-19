# trigger-session-end

> **Session Cleanup & Finalization** — Archive context and generate reports.

## Metadata

- **Event**: At session termination
- **Type**: Finalization
- **SLA**: < 2000ms (may be longer for large sessions)
- **Deterministic**: YES (deterministic cleanup)

## Description

Fires at session end. Performs:
1. Archive session context & conversation
2. Generate summary report (stats, decisions, errors)
3. Store sensitive data in secure storage
4. Cleanup temporary files
5. Log session metrics for analytics
6. Output: cleanup summary

## Output Format

```json
{
  "trigger_id": "trigger-session-end-20260317-145632",
  "session_duration_ms": 1800000,
  "total_prompts": 47,
  "total_tools_called": 152,
  "errors_count": 2,
  "sensitive_data_vaulted": 8,
  "cleanup_status": "complete"
}
```

## Cleanup Actions

1. Archive: /forge-journal
2. Remove: temporary files, scratch space
3. Secure: credentials, API keys
4. Compress: session logs
5. Notify: completion to user

**Status**: PROD-READY ✅
**Version**: 1.0.0
