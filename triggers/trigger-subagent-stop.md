# trigger-subagent-stop

> **Multi-Agent Coordination** — Stop orphaned subagents and consolidate results.

## Metadata

- **Event**: On user cancel OR timeout of subagent
- **Type**: Swarm Coordination
- **SLA**: < 1000ms
- **Deterministic**: YES (deterministic termination)

## Description

Fires when subagent needs stopping. Performs:
1. Send termination signal to subagent
2. Collect partial results (if any)
3. Consolidate partial outputs
4. Merge with parent context
5. Log reason for termination
6. Output: merged result or error

## Output Format

```json
{
  "trigger_id": "trigger-subagent-stop-20260317-145632",
  "subagent_id": "agent-explore-123",
  "reason": "user_cancel|timeout|error",
  "partial_results_collected": true,
  "merged_status": "partial",
  "results_count": 24
}
```

## Termination Reasons

- **user_cancel**: User explicitly stopped
- **timeout**: Exceeded max execution time
- **error**: Subagent encountered fatal error
- **resource_limit**: Hit memory/CPU limits

**Status**: PROD-READY ✅
**Version**: 1.0.0
