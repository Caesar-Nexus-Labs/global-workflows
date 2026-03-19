# global-workflows

106 slash commands + 20 trigger hooks for multi-agent AI swarms.

Works with Claude Code, Gemini CLI, Cursor, Codex, OpenCode, Antigravity.

---

## Install

```bash
git clone https://github.com/Caesar-Nexus-Labs/global-workflows.git
```

Pick your agent:

| Agent | Setup |
|-------|-------|
| Claude Code | [agents/claude/SETUP.md](agents/claude/SETUP.md) |
| Gemini CLI | [agents/gemini/SETUP.md](agents/gemini/SETUP.md) |
| Cursor | [agents/cursor/SETUP.md](agents/cursor/SETUP.md) |
| Codex CLI | [agents/codex/SETUP.md](agents/codex/SETUP.md) |
| OpenCode | [agents/opencode/SETUP.md](agents/opencode/SETUP.md) |
| Antigravity | [agents/antigravity/SETUP.md](agents/antigravity/SETUP.md) |

---

## Structure

```
commands/        ← 106 slash commands (forge-*, ops-*, market-*, nexus-*, spec-*, checkpoint-*)
triggers/        ← 20 lifecycle hooks (pre-tool, post-tool, session, quality gates)
agents/          ← per-agent setup guides
```

## Command Kits

| Kit | Prefix | Commands |
|-----|--------|----------|
| Engineer | `/forge-*` | plan, build, test, review, debug, refactor, git, docs |
| DevOps | `/ops-*` | deploy, k8s, terraform, monitoring, CI/CD, secrets |
| Marketing | `/market-*` | campaigns, SEO, analytics, content, ads, funnels |
| Compliance | `/nexus-*` | audit, risk, policy, remediation |
| Spec Pipeline | `/spec-*` | create → validate → decompose → execute |
| Checkpoints | `/checkpoint-*` | create, list, restore |

## Trigger Gates

Auto-fire on events. No manual invocation needed.

| Trigger | Event |
|---------|-------|
| `trigger-pre-tool` | Before every tool call — security gate |
| `trigger-post-tool` | After execution — verification |
| `trigger-session-start` | Session init |
| `trigger-session-end` | Cleanup + logging |
| `trigger-rust-verify` | `.rs` file save — compile + test |
| `trigger-lint` | File save — lint gate |
| `trigger-verify-before-done` | Block completion without evidence |
| `trigger-rules-reminder` | Each prompt — inject constraints |
| +12 more | See [triggers/](triggers/) |

---

*Part of [Caesar Nexus Labs](https://github.com/Caesar-Nexus-Labs)*
