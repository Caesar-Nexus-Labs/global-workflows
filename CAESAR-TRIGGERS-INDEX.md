# Caesar Nexus Strategic Trigger Index (Hooks Upgrade)

> Integrated Automation & Quality Gates for the Caesar Nexus Ecosystem. 100% Antigravity Trigger Standards.
> Trigger files are located in the `triggers/` subfolder.

## I. Lifecycle Event Triggers
These triggers respond to specific states within the Antigravity/Caesar Nexus session.

| Trigger Event | Description | Category |
| :--- | :--- | :--- |
| `trigger-session-start` | Orchestrates context loading at session genesis. | Session |
| `trigger-prompt-submit` | Injects rules and enriches context before LLM process. | Context |
| `trigger-pre-tool` | Deterministic guardrail before tool execution (Security). | Guard |
| `trigger-post-tool` | Post-execution analysis, type checking, and logging. | Quality |
| `trigger-session-end` | Final cleanup, report generation, and secure storage. | Finalization |
| `trigger-subagent-stop` | Mid-session coordination for multi-agent swarms. | Swarm |
| `trigger-verify-before-done` | Blocks premature task completion without verification. | Quality |
| `trigger-data-typecheck` | Type validation gate before data processing operations. | Quality |

## II. Built-in Strategic Triggers (Engineer Kit)
| Trigger Name | Logic Parent | Description |
| :--- | :--- | :--- |
| `trigger-rust-verify` | `rust-verify` | Real-time Rust Type/Boundary verification (`cargo check`). |
| `trigger-lint` | `lint-changed` | ISO standard code formatting (`cargo fmt`). |
| `trigger-rules-reminder` | `dev-rules-reminder`| Injects `forge-development-rules.md` into context. |
| `trigger-scout-block` | `scout-block` | Prevents aimless directory traversal/reconnaissance. |
| `trigger-edit-tracker` | `edit-count-tracker`| Triggers `/forge-refactor` after complexity limit. |
| `trigger-task-logger` | `task-completion-logger`| Records progress to `forge-journal.md`. |

## III. Marketing Strategic Triggers (Marketing Kit)
| Trigger Name | Logic Parent | Description |
| :--- | :--- | :--- |
| `trigger-market-data-audit` | NEW | Auto-validates data integrity before analytics. |
| `trigger-market-brand-gate` | NEW | Ensures "Caesar Nexus" branding on all exports. |
| `trigger-market-analytics-gate` | NEW | Validates analytics config before campaign launch. |
| `trigger-market-camp-sync` | NEW | Syncs campaign data across marketing channels. |
| `trigger-market-content-val` | NEW | Content quality validation before publication. |
| `trigger-market-intel-sync` | NEW | Triggers `/market-extract-pattern` on new competitors. |

## IV. Iron Laws
1. **Naming**: All hooks must be called `Trigger` and use `trigger-` prefix.
2. **Speed**: Execution must be < 5s to maintain Antigravity speed.
3. **Deterministic**: Logic must focus on hard-gates, not LLM ambiguity.
