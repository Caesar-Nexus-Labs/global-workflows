# global_workflows — Caesar Nexus Slash Commands

> Thư viện 104 slash commands + 16 triggers cho Caesar Nexus Swarm.
> Đây là T2 (Orchestration Layer) trong Skill Mesh Architecture.

## ⚠️ THIẾT QUÂN LUẬT

**NGHIÊM CẤM:**
- Tạo file không theo naming convention
- Tạo file `.sh`, `.py`, `.js` ở đây (chỉ `.md` files)
- Xóa hoặc rename file đang được reference trong CAESAR-SLASH-COMMANDS.md
- Mix planning và execution trong cùng 1 command

## Naming Convention

| Pattern | Category | Ví dụ |
|---------|----------|-------|
| `forge-*.md` | Engineer Kit | `forge-plan.md` |
| `ops-*.md` | DevOps Kit | `ops-deploy.md` |
| `market-*.md` | Marketing Kit | `market-campaign.md` |
| `spec-*.md` | Spec Kit | `spec-create.md` |
| `nexus-*.md` | Compliance Kit | `nexus-audit.md` |
| `checkpoint-*.md` | Checkpoint Kit | `checkpoint-create.md` |
| `trigger-*.md` | Trigger Hooks | `trigger-pre-tool.md` |

## Iron Laws

1. `/forge-brainstorm` = BRAINSTORM ONLY — không bao giờ thực thi
2. `/forge-plan` = PLAN WRITING ONLY — không thực thi
3. `/forge-execute-plan` = EXECUTION ONLY — không brainstorm/plan
4. Mọi command mới PHẢI được add vào `CAESAR-SLASH-COMMANDS.md`

## Files Quan Trọng

- [CAESAR-SLASH-COMMANDS.md](CAESAR-SLASH-COMMANDS.md) — Master index tất cả commands
- [SKILLS_INTEGRATION_MAP.md](SKILLS_INTEGRATION_MAP.md) — T1+T2+T3 integration map
- [CAESAR_SWARM_LINKING.md](CAESAR_SWARM_LINKING.md) — Swarm linking reference

## Liên kết

- Swarm Hub: `D:\Caesar-Nexus-Labs-Internal\brain_data\swarm_context.json`
- Bridge Router: `D:\Caesar-Nexus-Labs-Internal\skills_core\`
- Domain Skills: `D:\Caesar-Nexus-Labs-Internal\skills_repo\`
