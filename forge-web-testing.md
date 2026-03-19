---
name: /forge-web-testing
description: Specialized E2E and component testing.
category: Testing
status: Stable
methodology: Caesar Nexus Logic
---

# Web Testing Workflow (/forge-web-testing)

## 1. What This Workflow Does
Specialized E2E and component testing for web applications. Uses Playwright/Cypress for browser automation and Vitest/Jest for component logic.

## 2. Command Syntax
```bash
/forge-web-testing [e2e|unit|visual]
```

## 3. Operations
1. **Visual Regression**: Compares screenshots of UI components against baselines.
2. **E2E Flow**: Simulates user journeys (Login, Checkout, etc.).
3. **Performance**: Audits Lighthouse scores and Core Web Vitals.
