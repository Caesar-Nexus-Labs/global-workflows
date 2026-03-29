# Caesar Agents

This folder is the public home for Caesar client setup surfaces.

Contents:
- per-client setup guides
- public bootstrap notes for supported agents
- repo-local references to `commands/` and `triggers/`

This repository intentionally excludes:
- private persona registries
- internal runtime state
- private skill catalogs
- internal adapter payloads

Reading order:
1. start with the client-specific `SETUP.md`
2. confirm the command surface under `../commands/`
3. confirm lifecycle gates under `../triggers/`

Identity rule:
- these files describe how clients consume the public Caesar surface
- they must not redefine or shadow command identifiers
- they must stay public-safe and repo-local
- they must not reference private absolute paths or internal-only repositories

Update discipline:
- keep agent file names stable
- keep command and trigger names identical to the files under `../commands/` and `../triggers/`
- document only what a public user can infer from this repository itself
