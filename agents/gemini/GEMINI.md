# Caesar Nexus — Global Workflows Context

This session has access to the full Caesar Nexus slash command library and lifecycle triggers.

## Slash Commands (105 total)
- /forge — Engineering orchestration
- /forge-* — Engineering workflows (brainstorm, plan, deploy, debug, review, etc.)
- /ops-* — DevOps (deploy, k8s, terraform, monitoring, incidents, etc.)
- /market-* — Marketing (ads, analytics, SEO, content, campaigns, etc.)
- /spec-* — Spec management (create, decompose, execute, validate)
- /nexus-* — Compliance (audit, risk, remediate, report, validate)
- /checkpoint-* — Checkpoints (create, list, restore)

## Lifecycle Triggers (20 total, in triggers/)
Enforced via ~/.gemini/settings.json hooks.
- Session: trigger-session-start, trigger-session-end
- Tool: trigger-pre-tool, trigger-post-tool, trigger-subagent-stop
- Quality: trigger-lint, trigger-rust-verify, trigger-verify-before-done, trigger-data-typecheck
- Context: trigger-rules-reminder, trigger-prompt-submit
- Tracking: trigger-edit-tracker, trigger-scout-block, trigger-task-logger
- Marketing: trigger-market-analytics-gate, trigger-market-brand-gate, trigger-market-camp-sync, trigger-market-content-val, trigger-market-data-audit, trigger-market-intel-sync

## Source of Truth
Use the active `caesar-builder` clone that provides `commands/` and `triggers/`.
