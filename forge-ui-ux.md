---
name: /forge-ui-ux
description: High-fidelity premium design with Deep Platform-Specific Orchestration (Industry Standard).
category: Development
status: Stable
methodology: Caesar Nexus Logic
---

# Premium UI/UX Design (**[/forge-ui-ux](./forge-ui-ux.md)**)

## 1. Description
The "Aesthetic Vanguard". Orchestrates the creation of stunning, high-performance user interfaces tailored specifically for Desktop, Mobile, or Web environments. Adheres strictly to **Apple Human Interface Guidelines (HIG)**, **Microsoft Fluent Design**, and **Material Design 3**.

## 2. Caesar Nexus Execution Loop

### Phase 1: Visual Scouting & Environment Audit
1. **Platform Audit**: Identify the target environment (Desktop/Mobile/Web) by pulsing **[/forge-scout](./forge-scout.md)**.
2. **Standard Pulse**: Trigger **[trigger-rules-reminder](./trigger-rules-reminder.md)** to load platform-specific design constraints from **[/forge-development-rules](./forge-development-rules.md)**.
3. **Inspiration Discovery**: Invoke **[/market-persona](./market-persona.md)** to align aesthetics with the psychological triggers of the target audience.
4. **Brand Identity Lock (MANDATORY)**: Before writing any CSS or component code, read and internalize:
   - **Color System**: `D:\Caesar-Nexus-Labs-Internal\docs\specs\caesar-branding-color-system-design.md` — Sage Green OKLCH token system, semantic variants, forbidden patterns
     - **Sage Green Primary** (ONLY): `oklch(72.7% 0.144 137.1)` / hex `#7DB87D`
     - **Light variant**: `oklch(82.9% 0.107 137.6)` / hex `#A8D5A8`
     - **Dark variant**: `oklch(47.7% 0.130 136.4)` / hex `#3A6A3A`
     - **❌ FORBIDDEN**: Emerald (`rgba(16, 185, 129)`), cyan, or any non-sage-green colors without explicit project override
   - **Design Reference**: `D:\Caesar-Nexus-Labs-Internal\caesar-nexus-desktop` — Canonical implementation (verify globals.css for OKLCH tokens, app.css for component patterns)
   - **Enforcement**: All color choices MUST use Sage Green OKLCH tokens. No ad-hoc colors. Violations = blocked.

### Phase 2: Platform-Specific Engineering Laws

> **Stack Mandate (2026)** — Approved stacks per environment:
>
> | Platform | Frontend | Backend | Deploy |
> |----------|----------|---------|--------|
> | **Web** | SvelteKit 2 + Svelte 5 **OR** Next.js 15 (React 19) — choose per project | Axum 0.8 or Actix-web 4 (Rust — mandatory) | Vercel (primary) |
> | **Desktop** | Svelte + Tauri 2.0 (3-5MB binary) | Rust (Tauri core — mandatory) | Tauri build pipeline |
> | **Mobile** | Flutter 3.x (cross-platform, best perf) or Capacitor (web code reuse) | Rust or Flutter-native | App Store / Play Store |
>
> **Framework selection guide:**
> - **SvelteKit** — default for new web projects; best performance, minimal overhead, Vercel-native
> - **Next.js 15** — choose when: existing React codebase, large team familiar with React, or rich ecosystem needed (RSC, etc.)
> - **Tauri** — mandatory for all desktop apps; Electron forbidden (150MB vs 5MB)
> - **Flutter** — default mobile; React Native only if team is React-only
>
> **Related skills:** [/cn:sveltekit-mastery](../../skills_repo/c73-sveltekit-mastery/skill.md) | [c70-tauri-desktop-ui](../../skills_repo/c70-tauri-desktop-ui/SKILL.md)

#### 🖥️ [DESKTOP] Native Precision (OS-Native Core)
1. **Layout Architecture**: 
   - **Modular Pane System**: Implement a Sidebar-Detail-Inspector layout. Pulse **[/forge-research](./forge-research.md)** for native pane behavior. Invoke **[/forge-scout](./forge-scout.md)** to verify existing window/workspace constraints.
   - **Grid Standard**: Enforce an **8px Baseline Grid** for all layouts and a **4px Soft Grid** for component internals.
2. **Visual Fidelity**:
   - **Backdrop Effects**: Mandatory use of Mica/Acrylic (Windows) or Vibrancy (macOS) for fixed panes.
   - **Tabular Numerics**: Technical data columns MUST use `font-variant-numeric: tabular-nums`. Pulse **[/forge-optimize](./forge-optimize.md)** to verify density and alignment compliance.
3. **Interaction Model**:
   - **Precision Targeting**: Small interactive elements (24px-32px) permitted.
   - **Keyboard First**: Map global hotkeys (e.g., CMD/CTRL + K). Pulse **[/forge-problem-solving](./forge-problem-solving.md)** for hotkey conflict resolution.
   - **Contextual Access**: Implement native-style right-click context menus. Invoke **[/market-scout-logic](./market-scout-logic.md)** to deconstruct native interaction models.

#### 📱 [MOBILE] Touch Ergonomics (Device-Native Core)
> **Stack**: Flutter 3.x (default) or Capacitor (web code reuse). See Stack Mandate above.
1. **Ergonomic Layout**:
   - **Touch Targets**: Minimum **44pt x 44pt** for all interactive elements. Invoke **[/forge-research](./forge-research.md)** for thumb-reach pattern auditing.
   - **Thumb Zone**: Place primary actions (CTAs) within the bottom 60% of the screen.
2. **Interface Patterns**:
   - **Single Column**: Default to vertical stacks. Pulse **[/forge-scout](./forge-scout.md)** to identify platform-specific native UI components before cooking.
   - **Typography**: Minimum **16pt** for body text.
   - **Flutter**: Use Material 3 widgets (`ThemeData.useMaterial3 = true`) or Cupertino on iOS. Never custom-paint standard controls.
3. **Navigational Engineering**:
   - **Gesture Flow**: Swipe-to-back and Pull-to-refresh mandatory. Invoke **[/spec-create](./spec-create.md)** for gesture-mapping.
   - **Native Feedback**: Integrate haptic pulses (`HapticFeedback` on Flutter). Pulse **[/forge-problem-solving](./forge-problem-solving.md)** for feedback-state mapping.

#### 🌐 [WEB] Fluid Scalability (Browser-Standard Core)
> **Stack**: SvelteKit 2 + Svelte 5 (default) or Next.js 15. Design system: shadcn-svelte + Tailwind CSS v4. See Stack Mandate above.
1. **Dynamic Grid**:
   - Use **Fluid Containers** (CSS Grid/Flex). Pulse **[/forge-research](./forge-research.md)** for modern web layout strategies.
   - **Tailwind v4**: Use `@container` queries for component-level responsiveness. No fixed breakpoints in component internals.
2. **Standard Compliance**:
   - **WCAG Accessibility**: Ensure AA/AAA contrast ratios and ARIA tree compliance. Pulse **[/spec-validate](./spec-validate.md)** to audit accessibility.
   - **Typography**: Use `clamp()` for fluid font scaling. shadcn-svelte uses OKLCH color tokens — maintain token system, never hardcode colors.
   - **Typography Hard Limits (Web & Desktop HUD)**:
     - **Minimum font size**: `11px` for any visible text. `text-[6px]`→`text-[10px]` Tailwind utilities are **FORBIDDEN**.
     - **Label minimum**: `11px` for UI labels (`.hud-label`, `.data-label`, etc.).
     - **Body minimum**: `13px` for readable prose/logs.
     - **Minimum opacity for text**: `0.5` (50%). `opacity-30`, `opacity-20`, `opacity-10` on text are **FORBIDDEN**.
     - **Contrast floor**: Text color must achieve contrast ratio ≥ 4.5:1 against its background (WCAG AA). Verify with oklch contrast calculator before shipping.
     - **Uppercase + monospace**: Allowed only at `≥ 10px`. Uppercase tracking (`letter-spacing > 0.15em`) forbidden below `11px`.
     - **HUD/cyberpunk aesthetic exception**: Decorative non-readable elements (scanlines, noise) exempt. All text conveying information is NOT exempt.
3. **Performance Metrics**:
   - **Core Web Vitals**: Target **LCP < 2.5s**, **INP < 200ms**, **CLS < 0.1**. (*FID deprecated 2024 — use INP.*) Pulse **[/forge-optimize](./forge-optimize.md)** to verify DOM depth and asset weight.
   - **SSR Strategy**: Default to SvelteKit SSR (`+page.server.ts`) for data-heavy pages. Use CSR only for real-time/interactive UIs. Never ship a blank shell for SEO-sensitive routes.
   - **Image**: `<enhanced:img>` for local assets (auto avif/webp). `fetchpriority="high"` on LCP image. `loading="lazy"` on below-fold.

### Phase 3: Technical Implementation
1. **Blueprint Sync**: Pulse **[/forge-plan](./forge-plan.md)** (UI mode) ensuring technical tokens match the selected platform's laws.
2. **Component Cooking**: Invoke **[/forge-cook](./forge-cook.md)** for production implementation.

### Phase 4: Verification & Polish
1. **Environment Audit**: Verify 60fps performance and zero layout leakage.
2. **Aura Verification**: Pulse **[/forge-review](./forge-review.md)** to ensure the design feels "Native" and "Premium," not just functional.

## 3. Iron Laws
- **Strict Differentiation**: Never use mobile-first "Hamburger" menus for Desktop apps if window width allows for a Sidebar.
- **Density Mandate**: Desktop apps MUST achieve 3x data density compared to web counterparts.
- **Interaction Purity**: No hover effects on Mobile; no oversized "touch" buttons on Desktop.
- **English Standard**: All CSS classes, briefs, and documentation must be in English.
- **Typography Floor**: No text below `11px`. No text opacity below `50%`. Contrast ratio ≥ 4.5:1 mandatory. HUD aesthetics do NOT override readability for informational text.
- **Zero Hardcoded Micro-Text**: `text-[6px]`, `text-[7px]`, `text-[8px]`, `text-[9px]`, `text-[10px]` Tailwind utilities are banned in production UI. Refactor to design token or minimum `text-[11px]`.
- **Semantic HTML First**: Interactive elements must use `<button>`, `<a>`, or proper ARIA roles. Div-buttons forbidden.
- **Brand Color Mandatory**: ALL color usage must reference `caesar-branding-color-system-design.md` Sage Green OKLCH tokens. Enforcement:
  - **Web/CSS**: Prefer OKLCH format `oklch(72.7% 0.144 137.1)` (Tailwind v4 native, AI-generation compatible)
  - **Hex fallback**: `#7DB87D` permitted ONLY for backward compatibility; prioritize OKLCH in new code
  - **FORBIDDEN**: Hardcoded non-sage-green colors (emerald `rgba(16, 185, 129)`, cyan, accent palettes, etc.)
  - **Project override**: Explicit overrides MUST be documented in project-level spec file (e.g., "Caesar Remote uses cyan for VPN status — exception due to [reason]"). No undocumented ad-hoc colors.
  - **Reference check**: Always verify colors against canonical reference `D:\Caesar-Nexus-Labs-Internal\caesar-nexus-desktop/src/globals.css` before shipping.
- **Reference Implementation**: `D:\Caesar-Nexus-Labs-Internal\caesar-nexus-desktop` is the canonical design reference. Check it before inventing new patterns.
