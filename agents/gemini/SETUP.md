# Setup — Gemini CLI

## Installation

1. Clone this repo:
```bash
git clone https://github.com/Caesar-Nexus-Labs/caesar-builder.git
```

2. Copy or symlink `GEMINI.md` to your project root (Gemini CLI auto-loads it):
```bash
cp /path/to/caesar-builder/agents/gemini/GEMINI.md ~/your-project/GEMINI.md
# or symlink:
ln -s /path/to/caesar-builder/agents/gemini/GEMINI.md ~/your-project/GEMINI.md
```

3. Configure triggers in `~/.gemini/settings.json`:
```json
{
  "autoConfigureMaxOutputTokens": true,
  "triggerSettings": {
    "sessionStartTrigger": "/path/to/caesar-builder/triggers/trigger-session-start.md",
    "sessionEndTrigger": "/path/to/caesar-builder/triggers/trigger-session-end.md",
    "promptSubmitTrigger": "/path/to/caesar-builder/triggers/trigger-prompt-submit.md"
  }
}
```

## Commands available
See [commands/](../../commands/) — 106 slash commands across 6 kits.

## Triggers available
See [triggers/](../../triggers/) — 20 lifecycle hooks.
