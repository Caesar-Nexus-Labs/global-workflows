---
name: /forge-test
description: Mandatory verification workflow enforcing the TDD (Red-Green-Refactor) loop and high-coverage standards.
category: Quality & Testing
status: Stable
methodology: Caesar Nexus Logic
---

# Comprehensive Testing (/forge-test)

## 1. Description
Mandatory verification workflow enforcing the TDD (Red-Green-Refactor) loop and high-coverage standards.

## 2. Testing Tiers
- **Unit Tests**: Isolated logic testing for functions and components.
- **Integration Tests**: Verification of module interactions and API flows.
- **E2E Tests**: Full user-flow simulation (Mandatory for critical paths).
- **Security Tests**: Brute force, unauthorized access, and data leaking simulations.

## 3. Caesar Nexus Testing Flow
1. **Red Phase**: Write a test that fails due to missing feature or identified bug.
2. **Green Phase**: Implement logic until the test passes.
3. **Verification**: Run the full test suite with `--coverage`.
4. **Regression Check**: Ensure no existing functionality is broken.
5. **Handoff**: Success report saved to `reports/test-*.md`.

## 4. Quality Gates
- **Coverage**: Minimum 100% for core business logic.
- **Integrity**: Tests must be hermetic (No external side effects).
- **Performance**: Tests must execute in the optimized time-frame.

## 5. Iron Laws
- **TDD Enforcement**: No code without a failing test first (except for configuration).
- **Reproduction**: Debugging MUST start with a failing test case.
- **Zero Flakiness**: Any unstable test must be fixed or isolated; never ignored.

