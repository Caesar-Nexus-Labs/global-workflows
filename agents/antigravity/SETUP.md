# Setup — Antigravity Brain

## Installation (Internal)

This is the native environment. Workflows are already loaded via:
- Commands: the active local `caesar-builder` clone
- Triggers: bound in `~/.gemini/settings.json`
- GEMINI.md: auto-loaded at session start

This repo remains the distribution bundle for the native environment. The internal `caesar-control-plane` repository remains the canonical source of truth for workflow governance, command routing, and registry decisions.

## For fresh installs

1. Clone:
```bash
git clone https://github.com/Caesar-Nexus-Labs/caesar-builder.git \
  $HOME/.gemini/antigravity/caesar-builder
```

2. Bind triggers in `~/.gemini/settings.json` (see `agents/gemini/SETUP.md` for format).

3. GEMINI.md auto-discovery: Antigravity loads from working directory → `~/.gemini/` → global.

## Commands available
See [commands/](../../commands/) — 105 slash commands across 6 kits.

## Triggers available
See [triggers/](../../triggers/) — 20 lifecycle hooks, all active by default in Antigravity.
