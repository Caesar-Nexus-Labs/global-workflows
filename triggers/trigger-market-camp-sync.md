---
name: trigger-market-camp-sync
description: Multi-channel synchronization and coordination trigger.
event: trigger-subagent-stop
logic_source: claudekit-mkt Campaign Coordination
---

# Trigger: Campaign Sync (`trigger-market-camp-sync`)

## 1. Description (Ruột Claudekit Strategy)
Synchronizes progress between content production, email automation, and ad management during a multi-channel campaign launch. It ensures all "Vệ tinh" (satellites) are aligned before the final "Go-Live" signal.

## 2. Execution Logic
- **Invoke Event**: `trigger-subagent-stop`.
- **Action**:
    1. Update the `Campaign Dashboard` with the latest task completion status.
    2. If all assets (Email + Blog + Ads) are marked as `READY`, trigger the `/market-campaign` finalize phase.
    3. Broadcast the "Campaign Readiness" report to the `Brand Manager`.

## 3. Iron Laws
- **Coordination**: No channel launches until 100% of the cross-channel assets are verified and synced.
- **Visibility**: Real-time status update to the `Master Plan` artifact.
