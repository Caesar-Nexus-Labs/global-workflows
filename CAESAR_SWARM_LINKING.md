---
name: Caesar Nexus Swarm Linking
description: Master reference for Caesar integration with Multi-CLI Swarm
version: 1.0
linked_to: D:/Caesar-Nexus-Labs-Internal/brain_data/SWARM_SKILLS_INTEGRATION.md
---

# Caesar Nexus → Swarm Integration Reference

## Overview

Caesar Nexus slash commands are integrated into the Multi-CLI Swarm via:
- **Swarm Hub**: `D:\Caesar-Nexus-Labs-Internal\brain_data\swarm_context.json`
- **Skills Router**: `D:\Caesar-Nexus-Labs-Internal\skills_core\`
- **Domain Experts**: `D:\Caesar-Nexus-Labs-Internal\skills_repo\`

This document ensures Caesar commands can coordinate with Superpowers and access the broader skill ecosystem.

---

## Command Kits & Routing

### Engineer Kit (/forge-*)
| Command | Location | Routes To |
|---------|----------|-----------|
| `/forge-brainstorm` | forge-brainstorm.md | skills_core/c15-brainstorm/ |
| `/forge-plan` | forge-plan.md | skills_core/c15-plan/ |
| `/forge-execute-plan` | forge-execute-plan.md | brain_data/swarm_context.json |
| `/forge-debug` | forge-debug.md | skills_repo/c01-debug-* |
| `/forge-review` | forge-review.md | skills_core/c12-audit/ |
| `/forge-research` | forge-research.md | skills_repo/c01-* (domain) |
| `/forge-scout` | forge-scout.md | skills_repo/c01-* (architecture) |

### DevOps Kit (/ops-*)
| Command | Location | Routes To |
|---------|----------|-----------|
| `/ops-deploy` | ops-deploy.md | skills_repo/c01-deployment-* |
| `/ops-infra-plan` | ops-infra-plan.md | skills_repo/c01-aws-* |
| `/ops-k8s` | ops-k8s.md | skills_repo/c01-kubernetes-* |
| `/ops-terraform` | ops-terraform.md | skills_repo/c01-iac-* |

### Marketing Kit (/market-*)
| Command | Location | Routes To |
|---------|----------|-----------|
| `/market-plan` | market-plan.md | skills_repo/c01-marketing-* |
| `/market-campaign` | market-campaign.md | skills_repo/c01-campaign-* |
| `/market-write` | market-write.md | skills_repo/c01-copywriting-* |
| `/market-ads` | market-ads.md | skills_repo/c01-advertising-* |

### Specification Kit (/spec-*)
| Command | Location | Routes To |
|---------|----------|-----------|
| `/spec-create` | spec-create.md | skills_core/c15-docs/ |
| `/spec-validate` | spec-validate.md | skills_core/c12-audit/ |
| `/spec-decompose` | spec-decompose.md | skills_core/c15-plan/ |
| `/spec-execute` | spec-execute.md | brain_data/swarm_context.json |

### Trigger Hooks (trigger-*)
| Trigger | Location | Routes To |
|---------|----------|-----------|
| `trigger-pre-tool` | trigger-pre-tool.md | skills_core/c12-compliance/ |
| `trigger-post-tool` | trigger-post-tool.md | skills_core/c12-audit/ |
| `trigger-session-end` | trigger-session-end.md | brain_data/swarm_context.json |

---

## Integration Path

```
User → Caesar command (e.g., /forge-brainstorm)
         ↓
Load command from C:\Users\admin\.gemini\antigravity\global_workflows\
         ↓
[LINKING] Write to swarm_context.json:
  - action: "delegated"
  - target: "gemini|codex" (if needed)
  - message: "Task details"
         ↓
Route to appropriate skills_core (c15-*, c12-*, c05-*)
         ↓
If domain expertise needed, delegate to skills_repo (c01-*)
         ↓
Update swarm_context.json with results
         ↓
Return to user
```

---

## Key References

**Master Integration Doc:**
- See: `D:\Caesar-Nexus-Labs-Internal\brain_data\SWARM_SKILLS_INTEGRATION.md`

**Swarm Coordination:**
- Orchestration Flow: `D:\Caesar-Nexus-Labs-Internal\brain_data\SWARM-ORCHESTRATION-FLOW.md`
- Agent Roles: `D:\Caesar-Nexus-Labs-Internal\brain_data\AGENT-ROLES-BLUEPRINT.md`
- Context State: `D:\Caesar-Nexus-Labs-Internal\brain_data\swarm_context.json`

**Skills Routing:**
- Core Router: `D:\Caesar-Nexus-Labs-Internal\skills_core\SKILLS_CORE_ROUTING.md` (TO CREATE)
- Repository: `D:\Caesar-Nexus-Labs-Internal\skills_repo\CATALOG.md`

**Caesar Commands Master:**
- Index: `C:\Users\admin\.gemini\antigravity\global_workflows\CAESAR-SLASH-COMMANDS.md`
- Integration Map: `C:\Users\admin\.gemini\antigravity\global_workflows\SKILLS_INTEGRATION_MAP.md`

---

## For Caesar Command Implementation

When implementing a new Caesar command:

1. **Reference brain_data**:
   ```markdown
   ## Swarm Coordination
   - Hub: D:\Caesar-Nexus-Labs-Internal\brain_data\swarm_context.json
   - Route: See CAESAR_SWARM_LINKING.md for routing logic
   ```

2. **Link to skills_core/skills_repo**:
   - Identify which c15-* (core process) or c01-* (domain) skill is needed
   - Include "See also: SWARM_LINKING" in command metadata

3. **Update swarm_context.json**:
   - Log agent delegation with timestamp
   - Record which skills were consulted
   - Update `current_instruction` field

---

## Status

✅ Caesar commands exist and are functional (104 commands + 16 triggers)
⏳ skills_core routing layer: Awaiting implementation
⏳ Linking files: Awaiting creation by Gemini CLI
⏳ Full swarm coordination: Awaiting verification by Codex CLI

---

**Last Updated**: 2026-03-17
**Author**: Claude Code (Architect)
**Implementation Owner**: Gemini CLI (Coder)
**Verification Owner**: Codex CLI (Logic)
