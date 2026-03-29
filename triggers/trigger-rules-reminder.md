---
name: trigger-rules-reminder
description: Automatically injects Caesar Nexus development rules and brand constraints.
event: trigger-prompt-submit
methodology: Caesar Nexus Logic
---

# Trigger: Rules Reminder (`trigger-rules-reminder`)

## 1. Description
A strategic context-injection trigger executed before every user prompt processing. It ensures the active agent is fully aligned with Caesar Nexus "Iron Laws", avoiding hallucinations or legacy external branding.

## 2. Trigger Logic
- **Invoke Event**: `trigger-prompt-submit`.
- **Action**:
    1. Read `commands/forge-development-rules.md`.
    2. Read `commands/forge-orchestration-protocol.md`.
    3. Prefix the user prompt with a "System Constraints" reminder block.
- **Verification**: Ensure zero legacy external references are present in the injected context.

## 3. Implementation (Deterministic)
```yaml
config:
  file_guards:
    - path: "commands/forge-development-rules.md"
      required: true
  injection_point: "prompt_prefix"
  iron_laws:
    - "Never mention legacy external tools or third-party brands."
    - "Follow ISO v1.1 standards."
    - "Embrace Caesar Nexus branding."
```
