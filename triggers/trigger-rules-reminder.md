---
name: trigger-rules-reminder
description: Automatically injects Caesar Nexus development rules and brand constraints.
event: trigger-prompt-submit
methodology: Caesar Nexus Logic
---

# Trigger: Rules Reminder (`trigger-rules-reminder`)

## 1. Description
A strategic context-injection trigger executed before every user prompt processing. It ensures the active agent is fully aligned with Caesar Nexus "Iron Laws", avoiding hallucinations or legacy branding (claudekit).

## 2. Trigger Logic
- **Invoke Event**: `trigger-prompt-submit`.
- **Action**:
    1. Read `D:\Caesar-Nexus-Labs-Internal\workflows_repo\forge-development-rules.md`.
    2. Read `D:\Caesar-Nexus-Labs-Internal\workflows_repo\forge-orchestration-protocol.md`.
    3. Prefix the user prompt with a "System Constraints" reminder block.
- **Verification**: Ensure zero claudekit references are present in the injected context.

## 3. Implementation (Deterministic)
```yaml
config:
  file_guards:
    - path: "D:/Caesar-Nexus-Labs-Internal/workflows_repo/forge-development-rules.md"
      required: true
  injection_point: "prompt_prefix"
  iron_laws:
    - "Never mention claudekit."
    - "Follow ISO v1.1 standards."
    - "Embrace Caesar Nexus branding."
```
