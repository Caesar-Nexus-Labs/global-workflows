# global-workflows

> Orchestration layer for multi-agent AI swarms. 106 slash commands + 20 trigger hooks.

Agent-model agnostic. Runs on Claude, Gemini, Codex, GPT — anything that reads markdown instructions.

---

## What this is

The T2 orchestration layer of the Caesar Nexus Skill Mesh. Slash commands define *what* agents do. Triggers define *when* they act, *what* they gate, and *how* they hand off.

This is not a prompt library. It's a workflow protocol — the coordination fabric between specialized agents in a swarm.

---

## Structure

```
global-workflows/
├── forge-*.md       # Engineer Kit  — plan, build, test, review, deploy
├── ops-*.md         # DevOps Kit    — infra, CI/CD, monitoring, secrets
├── market-*.md      # Marketing Kit — intel, content, campaigns, analytics
├── nexus-*.md       # Compliance Kit — audit, policy, risk, remediation
├── spec-*.md        # Spec Workflow  — create, validate, decompose, execute
├── checkpoint-*.md  # Checkpoint Kit — create, list, restore
└── triggers/
    ├── trigger-pre-tool.md        # Security gate before every tool call
    ├── trigger-post-tool.md       # Verification after execution
    ├── trigger-session-start.md   # Environment init at session genesis
    ├── trigger-session-end.md     # Cleanup and logging on exit
    ├── trigger-rust-verify.md     # Rust compile + test gate on .rs edit
    ├── trigger-lint.md            # Lint gate on file save
    ├── trigger-rules-reminder.md  # Inject constraints on each prompt
    ├── trigger-task-logger.md     # Continuous decision logging
    ├── trigger-verify-before-done.md  # Block completion without evidence
    └── ...10 more
```

---

## Kits

| Kit | Commands | Purpose |
|-----|----------|---------|
| Engineer | `/forge`, `/forge-plan`, `/forge-debug`, `/forge-review`, `/forge-test`, +18 | Full dev lifecycle |
| DevOps | `/ops-deploy`, `/ops-k8s`, `/ops-terraform`, `/ops-monitoring`, +8 | Infrastructure |
| Marketing | `/market-campaign`, `/market-seo`, `/market-analytics`, `/market-content`, +17 | Growth |
| Compliance | `/nexus-audit`, `/nexus-risk`, `/nexus-remediate`, +4 | Quality gates |
| Spec | `/spec-create`, `/spec-decompose`, `/spec-execute`, `/spec-validate` | Spec-to-code pipeline |

---

## Iron Laws

Commands are **role-separated** — no mixing planning and execution in one command:

- `/forge-brainstorm` = brainstorm only, never executes
- `/forge-plan` = writes plans only, never touches code
- `/forge-execute-plan` = executes only, never re-plans

Triggers are **always-on gates** — they fire automatically, not on demand.

---

## Usage

Drop commands into any agent's system prompt or invoke via your agent framework's slash command interface. Each `.md` file is a self-contained instruction set.

```bash
# Example: tell Claude to use this workflow
"Follow the instructions in forge-debug.md to investigate this issue."
```

Triggers integrate with framework hooks (Claude Code `hooks`, Gemini CLI `triggers`). See individual trigger files for event binding specs.

---

## Naming Convention

| Prefix | Kit | Example |
|--------|-----|---------|
| `forge-*` | Engineer | `forge-plan.md` |
| `ops-*` | DevOps | `ops-deploy.md` |
| `market-*` | Marketing | `market-campaign.md` |
| `nexus-*` | Compliance | `nexus-audit.md` |
| `spec-*` | Spec Pipeline | `spec-create.md` |
| `checkpoint-*` | Checkpoints | `checkpoint-create.md` |
| `trigger-*` | Hooks | `trigger-pre-tool.md` |

---

*Part of the [Caesar Nexus Labs](https://github.com/Caesar-Nexus-Labs) ecosystem.*
