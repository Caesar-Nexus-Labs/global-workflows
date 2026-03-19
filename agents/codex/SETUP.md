# Setup — OpenAI Codex CLI

## Installation

1. Clone this repo:
```bash
git clone https://github.com/Caesar-Nexus-Labs/global-workflows.git
```

2. Add to your `AGENTS.md`:
```markdown
# Caesar Nexus Workflows
Available commands: /path/to/global-workflows/commands/
Triggers: /path/to/global-workflows/triggers/
Use /forge, /forge-plan, /ops-deploy, etc. as described in each .md file.
```

3. Invoke via Codex CLI:
```bash
codex --full-auto "Follow forge-debug.md to investigate this issue"
```

## Commands available
See [commands/](../../commands/) — 106 slash commands across 6 kits.
