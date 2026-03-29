---
name: trigger-data-typecheck
description: High-fidelity TypeScript type checking for changed files (RE-ENGINEERED).
event: trigger-post-tool
matcher: ".*\\.ts$|.*\\.tsx$"
---

# Trigger: Data TypeCheck (`trigger-data-typecheck`)

## 1. Description
This trigger enforces strict TypeScript type checking immediately after a tool modifies `.ts` or `.tsx` files. It prevents the introduction of type errors into the codebase by running incremental compilation.

## 2. Execution Logic
- **Matcher**: `Edit`, `Write`, `MultiEdit` on TypeScript files.
- **Action**:
    1. Invoke `tsc --noEmit --incremental` on the specific changed files.
    2. Capture diagnostic output.
    3. If errors exist, inject them back into the agent context with high-priority "FIX-REQUIRED" metadata.
- **Performance Heuristic**:
    - If execution > 8s, switch to `fork-tsc` or background check with a ⚠ notification.

## 3. Iron Laws
- **Strictness**: Must never skip a type check on core business logic files.
- **Feedback**: Results must include line numbers, error codes, and suggested fixes from the TS language server.
