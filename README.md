# global-workflows

106 slash commands + 20 trigger hooks for multi-agent AI swarms.

Works with Claude Code, Gemini CLI, Cursor, Codex, OpenCode, Antigravity.

---

## Install

```bash
git clone https://github.com/Caesar-Nexus-Labs/global-workflows.git
```

Pick your agent:

| Agent | Setup guide |
|-------|-------------|
| Claude Code | [agents/claude/SETUP.md](agents/claude/SETUP.md) |
| Gemini CLI | [agents/gemini/SETUP.md](agents/gemini/SETUP.md) |
| Cursor | [agents/cursor/SETUP.md](agents/cursor/SETUP.md) |
| Codex CLI | [agents/codex/SETUP.md](agents/codex/SETUP.md) |
| OpenCode | [agents/opencode/SETUP.md](agents/opencode/SETUP.md) |
| Antigravity | [agents/antigravity/SETUP.md](agents/antigravity/SETUP.md) |

---

## Structure

```
commands/     106 slash commands
triggers/     20 lifecycle hooks
agents/       per-agent setup guides
```

---

## Command Kits

<details>
<summary><strong>Engineer Kit</strong> — /forge-* (32 commands)</summary>

| Command | Purpose |
|---------|---------|
| `/forge` | Primary dev orchestration |
| `/forge-plan` | Implementation blueprint (plan only) |
| `/forge-brainstorm` | Innovation & problem solving (plan only) |
| `/forge-execute-plan` | Execute pre-written plans |
| `/forge-bootstrap` | Launch feature from zero |
| `/forge-debug` | Forensic root cause analysis |
| `/forge-review` | Quality & security audit |
| `/forge-test` | TDD execution & verification |
| `/forge-refactor` | Optimization without side-effects |
| `/forge-clean` | Dead code removal |
| `/forge-git` | Semantic commits & branching |
| `/forge-docs` | Documentation management |
| `/forge-research` | Technical scouting |
| `/forge-mcp-builder` | MCP server scaffolding |
| `/forge-ui-ux` | Premium design & UX |
| `/forge-scout` | Codebase analysis |
| `/forge-finish-branch` | Branch review & merge |
| `/forge-port-feature` | Feature porting across codebases |
| `/forge-journal` | Decision logging |
| `/forge-watzup` | Project status report |
| + 12 more | See [commands/](commands/) |

</details>

<details>
<summary><strong>DevOps Kit</strong> — /ops-* (13 commands)</summary>

| Command | Purpose |
|---------|---------|
| `/ops-deploy` | Deployment orchestration |
| `/ops-k8s` | Kubernetes management |
| `/ops-terraform` | Infrastructure as code |
| `/ops-monitoring` | Observability setup |
| `/ops-incident` | Incident response |
| `/ops-secrets` | Secrets management |
| `/ops-setup-cicd` | CI/CD pipeline setup |
| `/ops-canary` | Canary deployment |
| `/ops-infra-plan` | Infrastructure planning |
| `/ops-cost-analysis` | Cloud cost optimization |
| `/ops-audit-infra` | Infrastructure audit |
| `/ops-validate-deploy` | Deployment validation |
| `/ops-status` | System status report |

</details>

<details>
<summary><strong>Marketing Kit</strong> — /market-* (27 commands)</summary>

| Command | Purpose |
|---------|---------|
| `/market-plan` | Strategy planning |
| `/market-campaign` | Campaign orchestration |
| `/market-content` | Content production |
| `/market-seo` | SEO optimization |
| `/market-analytics` | Data analysis |
| `/market-ads` | Paid advertising |
| `/market-email` | Email campaigns |
| `/market-social` | Social media |
| `/market-funnel` | Conversion funnel |
| `/market-virality` | Growth loops |
| `/market-persona` | Audience modeling |
| `/market-brand` | Brand identity |
| `/market-write` | Copywriting |
| + 14 more | See [commands/](commands/) |

</details>

<details>
<summary><strong>Compliance Kit</strong> — /nexus-* (8 commands) · <strong>Spec Pipeline</strong> — /spec-* (4) · <strong>Checkpoints</strong> — /checkpoint-* (3)</summary>

| Command | Purpose |
|---------|---------|
| `/nexus-audit` | Full compliance audit |
| `/nexus-risk` | Risk assessment |
| `/nexus-policy` | Policy enforcement |
| `/nexus-remediate` | Issue remediation |
| `/nexus-report` | Compliance reporting |
| `/nexus-validate-eng` | Engineering validation |
| `/nexus-validate-infra` | Infrastructure validation |
| `/nexus-validate-market` | Marketing validation |
| `/spec-create` | Generate technical spec |
| `/spec-validate` | Audit spec completeness |
| `/spec-decompose` | Break spec into tasks |
| `/spec-execute` | Orchestrate from spec |
| `/checkpoint-create` | Save project checkpoint |
| `/checkpoint-list` | List checkpoints |
| `/checkpoint-restore` | Restore checkpoint |

</details>

---

## Trigger Gates

Auto-fire on events. No manual invocation needed.

<details>
<summary><strong>All 20 triggers</strong></summary>

| Trigger | Event | Purpose |
|---------|-------|---------|
| `trigger-pre-tool` | Before tool call | Security gate |
| `trigger-post-tool` | After execution | Verification |
| `trigger-session-start` | Session init | Environment setup |
| `trigger-session-end` | Session close | Cleanup & logging |
| `trigger-prompt-submit` | Each prompt | Inject constraints |
| `trigger-rules-reminder` | Each prompt | Rules enforcement |
| `trigger-rust-verify` | `.rs` save | Compile + test gate |
| `trigger-lint` | File save | Lint gate |
| `trigger-verify-before-done` | Task completion | Block without evidence |
| `trigger-data-typecheck` | Data ops | Type validation |
| `trigger-edit-tracker` | File edit | Change logging |
| `trigger-task-logger` | Task events | Decision logging |
| `trigger-scout-block` | Scout ops | Scope enforcement |
| `trigger-subagent-stop` | Subagent exit | Cleanup gate |
| `trigger-market-analytics-gate` | Market data | Analytics validation |
| `trigger-market-brand-gate` | Brand ops | Brand consistency |
| `trigger-market-camp-sync` | Campaigns | Campaign sync |
| `trigger-market-content-val` | Content ops | Content validation |
| `trigger-market-data-audit` | Market data | Data audit |
| `trigger-market-intel-sync` | Intel ops | Intelligence sync |

</details>

---

*Part of [Caesar Nexus Labs](https://github.com/Caesar-Nexus-Labs)*
