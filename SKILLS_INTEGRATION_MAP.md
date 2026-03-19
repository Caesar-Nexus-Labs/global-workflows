# Caesar Nexus + Skills Integration Map

> Unified reference for integrating Process Skills (T1) + Caesar Slash Commands (T2) + Domain Skills (T3)
>
> **Last Updated**: 2026-03-17
> **Status**: Global integration ready for all sessions

---

## 🏗️ Skill Tier Architecture

```
T1: Process Skills (Built-in)
├─ superpowers:brainstorming
├─ superpowers:writing-plans
├─ superpowers:executing-plans
├─ superpowers:test-driven-development
├─ superpowers:verification-before-completion
└─ superpowers:systematic-debugging

T2: Caesar Slash Commands (104 commands + 16 triggers)
├─ /forge-* (Engineer Kit, 20 commands)
├─ /market-* (Marketing Kit, 25 commands)
├─ /spec-* (Spec Kit, 4 commands)
├─ /ops-* (DevOps Kit, 13 commands)
├─ /nexus-* (Compliance Kit, 6 commands)
├─ /checkpoint-* (Checkpoint Kit, 3 commands)
└─ trigger-* (16 lifecycle hooks)

T3: Domain Skills (50+ specialized)
├─ c01_api_security
├─ c01_auth_implementation
├─ c01_aws_penetration_testing
├─ c01_azure_identity_dotnet
├─ c01_attack_tree_construction
└─ ... (40+ more)

T4+: Custom Skills (reserved)
└─ (future domain-specific extensions)
```

---

## 🔗 Integration Workflow

### **Typical Execution Path:**

```
User Request
    ↓
T1: Process Skills: brainstorming (ideation phase)
    ├─ Generate ideas & options
    └─ If domain expertise needed: call T3 skill
         └─ /skill "cn:c01_api_security" (example)
    ↓
T2: /forge-plan (plan writing phase)
    ├─ Write implementation blueprint
    └─ If domain reference: call T3 skill
         └─ /skill "cn:c01_auth_implementation" (example)
    ↓
[USER REVIEWS PLAN]
    ↓
T2: /forge-execute-plan (execution phase)
    ├─ Execute plan phases sequentially
    ├─ Trigger: trigger-pre-tool, trigger-post-tool
    └─ If domain validation: call T3 skill
         └─ /skill "cn:c01_api_security" (verification)
    ↓
T1: Process Skills: verification-before-completion (quality gate)
    └─ Verify all deliverables
```

---

## 📋 Command-to-Skill Mapping

### **Engineer Kit → Domain Skills**

| Caesar Command | Domain Skill | Use Case |
|---|---|---|
| `/forge-plan` | `cn:c01_architecture_patterns` | Blueprint phase |
| `/forge-test` | `cn:c01_tdd_practices` | Test design |
| `/forge-api` | `cn:c01_api_security` | API design review |
| `/forge-better-auth` | `cn:c01_auth_implementation` | Auth implementation |
| `/forge-infra-design` | `cn:c01_aws_architecture` | Infrastructure design |
| `/forge-git` | `cn:c01_git_workflow` | Git strategy |

### **DevOps Kit → Domain Skills**

| Caesar Command | Domain Skill | Use Case |
|---|---|---|
| `/ops-deploy` | `cn:c01_deployment_strategies` | Deployment planning |
| `/ops-infra-plan` | `cn:c01_terraform_iac` | Infrastructure as Code |
| `/ops-k8s` | `cn:c01_kubernetes_patterns` | K8s deployment |
| `/ops-audit-infra` | `cn:c01_security_hardening` | Security audit |

### **Marketing Kit → Domain Skills**

| Caesar Command | Domain Skill | Use Case |
|---|---|---|
| `/market-write` | `cn:c01_copywriting_psychology` | High-conversion copy |
| `/market-seo` | `cn:c01_seo_technical` | SEO strategy |
| `/market-data-audit` | `cn:c01_data_governance` | Data quality |

### **Compliance Kit → Domain Skills**

| Caesar Command | Domain Skill | Use Case |
|---|---|---|
| `/nexus-validate-eng` | `cn:c01_engineering_standards` | Code quality gate |
| `/nexus-risk` | `cn:c01_threat_modeling` | Risk assessment |
| `/nexus-remediate` | `cn:c01_incident_response` | Issue remediation |

---

## ⚡ Quick Reference

### **Calling Domain Skills (T3):**

```bash
# In any Caesar command or Process Skills phase:
/skill "cn:c01_api_security"
/skill "cn:c01_auth_implementation"
/skill "cn:c01_aws_penetration_testing"

# List available skills:
ls D:\Caesar-Nexus-Labs-Internal\skills_repo\ | grep "^c01-"
```

### **Calling Caesar Commands (T2):**

```bash
# Planning phase:
/forge-brainstorm [prompt]
/forge-plan [requirements]

# Execution phase:
/forge-execute-plan --plan-file plan.md

# Specific domains:
/ops-deploy --environment prod
/market-campaign --campaign-name spring-2026
```

### **Calling Process Skills (T1):**

```bash
# Automatic via Caesar commands, or explicit:
/superpowers:brainstorming
/superpowers:writing-plans
/superpowers:verification-before-completion
```

---

## 🚨 Integration Rules (STRICT)

### **What Caesar Slash Commands Can Do:**
- ✅ Call Process Skills (T1) automatically
- ✅ Call domain skills (T3) via `/skill "cn:*"`
- ✅ Orchestrate full workflows
- ✅ Trigger hooks for audit/logging

### **What Process Skills Can Do:**
- ✅ Call Caesar commands (T2) for execution
- ✅ Call domain skills (T3) for expertise
- ✅ Enforce process discipline

### **What Domain Skills Can Do:**
- ✅ Provide expertise guidance
- ✅ Reference other domain skills
- ✅ Support Caesar commands

### **What NO ONE Can Do:**
- 🚫 Call T2 from T1 WITHOUT user approval
- 🚫 Load ALL domain skills into context
- 🚫 Bypass tier routing (always T1→T2→T3→T4)
- 🚫 Modify other team's skills without coordination

---

## 📍 File Locations (Global Reference)

```
Process Skills (T1):
  ~/.claude/plugins/cache/claude-plugins-official/superpowers/5.0.4/skills/

Caesar Slash Commands (T2):
  C:\Users\admin\.gemini\antigravity\global_workflows\

Domain Skills (T3):
  D:\Caesar-Nexus-Labs-Internal\skills_repo\

Configuration:
  C:\Users\admin\.claude\CLAUDE.md  (main)
  C:\Users\admin\.gemini\GEMINI.md  (synced)
```

---

## 🔄 Session Initialization

**On every session, Claude Code will:**
1. ✅ Load T1 (Process Skills) automatically
2. ✅ Load T2 (Caesar commands) from master index
3. ⚠️ Load T3 (Domain skills) on-demand only (via `/skill`)
4. ✅ Apply T4+ custom if defined

**No manual setup needed.** This integration map is global for all future sessions.

---

**Status**: ✅ INTEGRATION COMPLETE
**Validation**: 104 Caesar commands + 6 T1 skills + 50+ T3 skills ready
**Ready for**: Multi-agent coordination (Claude Code + Gemini CLI + Codex CLI)

