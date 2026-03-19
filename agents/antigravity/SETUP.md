# Setup — Antigravity Brain

## Installation (Internal)

This is the native environment. Workflows are already loaded via:
- Commands: `C:\Users\admin\.gemini\antigravity\caesar-builder\`
- Triggers: bound in `~/.gemini/settings.json`
- GEMINI.md: auto-loaded at session start

## For fresh installs

1. Clone:
```bash
git clone https://github.com/Caesar-Nexus-Labs/caesar-builder.git \
  C:/Users/admin/.gemini/antigravity/caesar-builder
```

2. Bind triggers in `~/.gemini/settings.json` (see `agents/gemini/SETUP.md` for format).

3. GEMINI.md auto-discovery: Antigravity loads from working directory → `~/.gemini/` → global.

## Commands available
See [commands/](../../commands/) — 106 slash commands across 6 kits.

## Triggers available
See [triggers/](../../triggers/) — 20 lifecycle hooks, all active by default in Antigravity.
