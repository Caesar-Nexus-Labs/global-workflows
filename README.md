# caesar-builder

Public command surface for Caesar Nexus: `105` slash commands, `20` lifecycle triggers, and per-agent setup guides.

## What This Repository Is

This repository is the public orchestration layer only:
- `commands/` defines the slash-command surface
- `triggers/` defines lifecycle gates
- `agents/` explains how supported clients load the surface

Treat this repository as the public contract for how Caesar clients discover and invoke workflows.

## What This Repository Is Not

This repository intentionally does **not** include:
- private runtime state
- internal ledgers or operator journals
- private skill bundles
- private persona registries
- internal adapter payloads
- workspace-state or deployment output

If a workflow depends on private runtime, private skills, or internal storage, that dependency must remain conceptual in this public surface. This repository must stay readable and safe on its own.

## Quick Start

```bash
git clone https://github.com/Caesar-Nexus-Labs/caesar-builder.git
```

## Repository Role

`caesar-builder` is the public onboarding and distribution surface for Caesar Nexus workflows.

The internal `caesar-control-plane` repository remains the canonical source of truth for workflow governance, command routing, registry decisions, and control-plane policy. Use this repo to install and consume the bundle; if public onboarding text here ever drifts from internal control-plane policy, trust the control-plane repository first.

Read in this order:
1. this `README.md`
2. [agents/README.md](agents/README.md)
3. the setup guide for your client
4. the specific file under [commands/](commands/) or [triggers/](triggers/) you plan to use

Pick your agent:

| Agent | Setup guide |
|-------|-------------|
| Claude Code | [agents/claude/SETUP.md](agents/claude/SETUP.md) |
| Gemini CLI | [agents/gemini/SETUP.md](agents/gemini/SETUP.md) |
| Cursor | [agents/cursor/SETUP.md](agents/cursor/SETUP.md) |
| Codex CLI | [agents/codex/SETUP.md](agents/codex/SETUP.md) |
| OpenCode | [agents/opencode/SETUP.md](agents/opencode/SETUP.md) |
| Antigravity | [agents/antigravity/SETUP.md](agents/antigravity/SETUP.md) |

## Structure

```text
commands/     105 slash commands
triggers/     20 lifecycle hooks
agents/       per-agent setup guides
```

## Repository Contract

These counts are canonical for the current public release:
- `105` command files in `commands/`
- `20` trigger files in `triggers/`
- supported client setup surfaces under `agents/`

If a README, setup guide, or command description claims a different count, the files on disk win. Public-facing docs should never invent commands that do not exist as files in this repository.

## Identifier Discipline

Public updates must preserve repository identifiers exactly as they exist on disk:
- command files keep their current slash-command identity
- trigger files keep their current trigger identity
- agent setup files must reference commands and triggers without renaming them

Do not publish documentation that:
- renames an existing command or trigger in prose
- introduces aliases that do not exist as files
- points to private absolute paths, private repo names, or internal runtime-only storage
- copies internal-only operating notes into this public repository

## Command Kits

<details>
<summary><strong>Engineer Kit</strong> — /forge-* (32 commands)</summary>

| Command | Purpose |
|---------|---------|
| `/forge` | Primary dev orchestration |
| `/forge-plan` | Implementation blueprint |
| `/forge-brainstorm` | Read-only strategic ideation |
| `/forge-execute-plan` | Execute pre-written plans |
| `/forge-bootstrap` | Launch a new project or major feature |
| `/forge-debug` | Forensic root cause analysis |
| `/forge-review` | Parallel quality and security audit |
| `/forge-test` | Verification and TDD enforcement |
| `/forge-refactor` | Optimization without side-effects |
| `/forge-clean` | Dead code removal |
| `/forge-git` | Semantic commits and branching |
| `/forge-docs` | Documentation management |
| `/forge-research` | Technical scouting |
| `/forge-mcp-builder` | MCP server scaffolding |
| `/forge-ui-ux` | Premium design and UX orchestration |
| `/forge-scout` | Codebase analysis |
| `/forge-finish-branch` | Branch review and merge |
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

## Trigger Gates

Auto-fire on events. No manual invocation needed.

<details>
<summary><strong>All 20 triggers</strong></summary>

| Trigger | Event | Purpose |
|---------|-------|---------|
| `trigger-pre-tool` | Before tool call | Security gate |
| `trigger-post-tool` | After execution | Verification |
| `trigger-session-start` | Session init | Environment setup |
| `trigger-session-end` | Session close | Cleanup and logging |
| `trigger-prompt-submit` | Each prompt | Inject constraints |
| `trigger-rules-reminder` | Each prompt | Rules enforcement |
| `trigger-rust-verify` | `.rs` save | Compile and test gate |
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

## Repository Boundary

Use this repository when you need:
- a public slash-command surface
- trigger definitions and wording
- setup guides for supported agent clients

Do not treat this repository as:
- the full Caesar control plane
- the runtime implementation
- a workspace-state store
- a private skills or persona registry

## Release Discipline

For public updates in this repository:
- preserve command and trigger identifiers exactly as filenames
- keep public docs repo-local and public-safe
- do not leak internal absolute paths, private repo names, or operator-only storage conventions
- prefer explicit boundary notes over ambiguous references to private infrastructure

## Contributors

Built and battle-tested across a multi-agent Caesar workflow stack.

| Agent | Role |
|-------|------|
| [Claude Code](https://claude.ai/code) | Primary architect and workflow author |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Orchestration and trigger binding |
| [Antigravity Brain](https://github.com/Caesar-Nexus-Labs) | Internal runtime and session management |
| [Codex CLI](https://github.com/openai/codex) | Task execution and code synthesis |

*Part of [Caesar Nexus Labs](https://github.com/Caesar-Nexus-Labs)*
