# trigger-market-intel-sync

> **Competitive Intelligence Sync** — Update market research and competitor data.

## Metadata

- **Event**: On schedule (daily or weekly) OR on /market-scout-logic call
- **Type**: Data Sync
- **SLA**: < 5000ms (may be longer for large datasets)
- **Deterministic**: YES (scheduled sync logic)

## Description

Fires on schedule to update competitive intelligence. Performs:
1. Poll competitive intelligence sources
2. Extract competitor product updates
3. Update /market-extract-pattern cache
4. Flag new competitive threats
5. Sync to analytics dashboard
6. Output: sync status & updates

## Output Format

```json
{
  "trigger_id": "trigger-market-intel-sync-20260317-145632",
  "sync_type": "scheduled|on_demand",
  "competitors_monitored": 12,
  "updates_found": 4,
  "threat_alerts": 1,
  "cache_updated": true,
  "sync_status": "complete"
}
```

## Schedule

- Default: Daily at 09:00 UTC
- Can be triggered on-demand by /market-scout-logic
- Lightweight: only deltas, not full re-scan

**Status**: PROD-READY ✅
**Version**: 1.0.0
