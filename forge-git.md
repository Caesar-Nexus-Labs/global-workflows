---
name: /forge-git
description: Advanced version control management and smart commit strategies.
category: DevOps & Version Control
status: Stable
methodology: Git Ops
---

# Advanced Version Control (/forge-git)

## 1. Smart Status (/git-status)
- **Action**: Aggregate changes and group them by type (feature, fix, refactor, style, docs).
- **Strategy**: Suggest a commit strategy based on the logical separation of changes.
- **Output**: Visual organization of modified files and suggested commit messages.

## 2. Smart Commit (/git-commit)
- **Action**: Generate high-fidelity, conventional commit messages.
- **Format**: `<type>(<scope>): <short summary>` followed by a detailed body and list of affected components.

## 3. Workflow Isolation (/git-worktree)
- **Action**: Manage parallel tasks using Git worktrees to prevent context switching friction.
- **Command**: Setup and cleanup of specialized task directories.

## 4. Caesar Nexus Quality Gate
- **Pre-commit**: Automatic invocation of `/forge-review --fast` to ensure zero syntax errors or leaked secrets.
- **Branding Check**: Ensure 1:1 match with Caesar Nexus naming conventions.

## 5. Iron Laws
- **Conventional Commits**: Mandatory adherence to the conventional commit standard.
- **Clean History**: Rebase and squash are preferred for maintaining a clean, linear project history.
- **Zero Secrets**: Absolute prohibition of committing sensitive data (secrets, keys, PII).

