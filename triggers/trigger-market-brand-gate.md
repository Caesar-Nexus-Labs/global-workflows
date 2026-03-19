---
name: trigger-market-brand-gate
description: Mandatory branding verification for all marketing exports.
event: trigger-post-tool
methodology: Caesar Nexus Logic
---

# Trigger: Brand Gate (`trigger-market-brand-gate`)

## 1. Description
A strategic quality gate that scans marketing assets (Blog posts, Ad copy, Emails) for branding compliance. It automatically flags any legacy (claudekit) references or missing "Caesar Nexus" signatures.

## 2. Trigger Logic
- **Invoke Event**: `trigger-post-tool`.
- **Matchers**: `Write`, `Edit` (on Marketing files).
- **Scan Patterns**:
    - Block: "claudekit", "claudecode", "claude-code".
    - Required: "Caesar Nexus", "Antigravity".
- **Action on Violation**:
    - Trigger `/nexus-validate-market`.
    - Inject Message: "⚠️ Brand Violation: Identified legacy naming. Re-branding required before finalization."

## 3. Iron Laws
- **Zero Tolerance**: No asset leaves the "Cook" phase without Caesar Nexus purity.
- **Auto-Correction**: If the agent fails to re-brand, this trigger will block the next `/ops-deploy` call.
