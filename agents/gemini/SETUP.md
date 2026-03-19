# Setup — Gemini CLI

## Installation

1. Clone this repo:
```bash
git clone https://github.com/Caesar-Nexus-Labs/global-workflows.git
```

2. Copy or symlink `GEMINI.md` to your project root (Gemini CLI auto-loads it):
```bash
cp /path/to/global-workflows/agents/gemini/GEMINI.md ~/your-project/GEMINI.md
# or symlink:
ln -s /path/to/global-workflows/agents/gemini/GEMINI.md ~/your-project/GEMINI.md
```

3. Configure triggers in `~/.gemini/settings.json`:
```json
{
  "autoConfigureMaxOutputTokens": true,
  "triggerSettings": {
    "sessionStartTrigger": "/path/to/global-workflows/triggers/trigger-session-start.md",
    "sessionEndTrigger": "/path/to/global-workflows/triggers/trigger-session-end.md",
    "promptSubmitTrigger": "/path/to/global-workflows/triggers/trigger-prompt-submit.md"
  }
}
```

## Commands available
See [commands/](../../commands/) — 106 slash commands across 6 kits.

## Triggers available
See [triggers/](../../triggers/) — 20 lifecycle hooks.
