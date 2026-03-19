# Setup — Claude Code

## Installation

1. Clone this repo:
```bash
git clone https://github.com/Caesar-Nexus-Labs/global-workflows.git
```

2. Add to your `CLAUDE.md` (global or project-level):
```markdown
# Slash Commands
Commands are in: /path/to/global-workflows/commands/
Triggers are in: /path/to/global-workflows/triggers/

Use /forge, /forge-plan, /ops-deploy, etc. as described in each .md file.
```

3. Configure hooks in `~/.claude/settings.json`:
```json
{
  "hooks": {
    "PreToolUse": [{ "command": "cat /path/to/global-workflows/triggers/trigger-pre-tool.md" }],
    "PostToolUse": [{ "command": "cat /path/to/global-workflows/triggers/trigger-post-tool.md" }],
    "UserPromptSubmit": [{ "command": "cat /path/to/global-workflows/triggers/trigger-rules-reminder.md" }]
  }
}
```

## Commands available
See [commands/](../../commands/) — 106 slash commands across 6 kits.

## Triggers available
See [triggers/](../../triggers/) — 20 lifecycle hooks.
