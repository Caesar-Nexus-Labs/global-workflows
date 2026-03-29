---
name: /forge-ui-ux
description: High-fidelity premium design with platform-aware orchestration and design-system derivation.
category: Development
status: Stable
methodology: Caesar Nexus Logic
---

# Premium UI/UX Design (**[/forge-ui-ux](./forge-ui-ux.md)**)

## 1. Description
Derives a complete design system from the product description before writing a single line of code: style, typography, density, timing, motion, and anti-patterns resolved first, then implemented for Desktop, Mobile, or Web. Adheres to **Apple HIG**, **Microsoft Fluent Design**, and **Material Design 3**.

## 2. Caesar Nexus Execution Loop

### Phase 0: Design-System Derivation (Mandatory)

Resolve these axes before implementation:

1. **Product Type**: developer tool, SaaS, dashboard, consumer app, landing page, mobile utility, AI product, healthcare, creative, finance.
2. **Visual Style**: minimalism, bento grid, glassmorphism, data-dense dashboard, aurora hero, HUD/cyberpunk, AI-native.
3. **Typography**: heading family, body family, data/code family, size floors, line-height, readability targets.
4. **Color Mode**: dark-first with immediate light overrides.
5. **Timing Class**: productivity `150ms`, dashboard `200-250ms`, consumer `200-300ms`, premium `400-600ms`.
6. **Anti-Patterns**: text below `11px`, opacity below `50%`, hover-only states on mobile, hamburger on desktop when a sidebar fits, div-buttons, hardcoded ad-hoc colors, more than two simultaneous animated elements.

### Default Caesar Brand Tokens

Use project-specific overrides if they exist. If not, default to:

```text
Brand:           oklch(62% 0.247 30)  /  #FF3E00
Hover:           oklch(67% 0.220 30)  /  #FF6130
Active:          oklch(55% 0.260 30)  /  #D93400
Dark BG:         oklch(8% 0 0)        /  #0D0D0D
Light BG:        oklch(98% 0 0)       /  #FAFAFA
Brand on light:  oklch(52% 0.247 30)  /  #C23000
```

Forbidden defaults: undocumented ad-hoc accents, emerald utility green as a primary brand, cyan as a default accent, and AI purple/pink gradients by habit.

### Phase 1: Visual Scouting & Environment Audit

1. **Platform Audit**: **[/forge-scout](./forge-scout.md)**
2. **Standard Pulse**: **[trigger-rules-reminder](../triggers/trigger-rules-reminder.md)** then **[/forge-development-rules](./forge-development-rules.md)**
3. **Persona Alignment**: **[/market-persona](./market-persona.md)**

### Phase 2: Stack Mandate (2026)

| Platform | Frontend | Backend | Deploy |
|----------|----------|---------|--------|
| **Web** | SvelteKit 2 + Svelte 5 or Next.js 15 | Axum 0.8 / Actix-web 4 (Rust) | Vercel |
| **Desktop** | Svelte + Tauri 2.0 | Rust (Tauri core) | Tauri pipeline |
| **Mobile** | Flutter 3.x or Capacitor | Rust or Flutter-native | App / Play Store |

Framework defaults:
- **SvelteKit** for new web projects
- **Next.js 15** when an existing React codebase or ecosystem requirement justifies it
- **Tauri** for desktop apps
- **Flutter** for mobile by default

### Phase 3: Platform Laws

#### Desktop
- Sidebar-detail-inspector layouts when density matters
- `8px` baseline grid and `4px` soft grid for internals
- `tabular-nums` on technical data
- Keyboard-first interactions and native-style context menus

#### Mobile
- Minimum `44pt x 44pt` targets
- Primary actions inside the reachable thumb zone
- Minimum `16px` body size
- Native gestures and tactile feedback where appropriate

#### Web
- Fluid containers and container queries
- `clamp()` for typography
- WCAG AA minimum
- No blank SSR shell for SEO-sensitive routes
- LCP `< 2.5s`, INP `< 200ms`, CLS `< 0.1`

### Phase 4: Technical Implementation

1. **Blueprint Sync**: **[/forge-plan](./forge-plan.md)** in UI mode
2. **Build**: **[/forge-cook](./forge-cook.md)**
3. **Verification**: **[/forge-review](./forge-review.md)** before delivery

## 3. Iron Laws

- **Platform Differentiation**: No hamburger on desktop when a sidebar fits. No hover-only UX on mobile.
- **Density Mandate**: Desktop should achieve materially higher information density than web.
- **Typography Floor**: No text below `11px`. No text opacity below `50%`. Minimum contrast `4.5:1`.
- **Zero Micro-Text**: `text-[6px]` through `text-[10px]` are forbidden in production UI.
- **Semantic HTML First**: Use `<button>`, `<a>`, and proper ARIA roles. Div-buttons are forbidden.
- **Dual Mode Delivery**: Ship dark and light mode together, with dark-first implementation and immediate light overrides.
- **Motion Discipline**: Respect `prefers-reduced-motion`; animate `transform` and `opacity` only; max two simultaneous animated elements.
- **English Standard**: CSS classes, component names, and UI documentation stay in English.
