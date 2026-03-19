# Caesar Nexus Agent Hierarchy (High-Fidelity)

> This document defines the official roles, interactions, and command mappings for all 70 agents (15 Engineer, 43 Marketing, 12 DevOps) within the Caesar Nexus ecosystem. Materialized from high-fidelity source ingestion.

## I. ENGINEER KIT (15 Agents)

### Tier 1: Planning & Orchestration
1. **Planner Agent**
   - **Role**: Primary strategy and roadmap architect. Coordinates research and feature decomposition.
   - **Commands**: `/forge-plan`, `/forge-brainstorm`.
2. **Project Manager Agent**
   - **Role**: Timeline tracker and resource coordinator. Monitors progress and blockers.
   - **Commands**: `/forge-project-management`, `/forge-watzup`.
3. **Brainstormer Agent**
   - **Role**: Creative problem solver and innovation scout. Explores alternative designs.
   - **Commands**: `/forge-brainstorm`, `/forge-plan`.

### Tier 2: Core Development
4. **Fullstack Developer Agent**
   - **Role**: End-to-end feature implementer (Frontend + Backend). 
   - **Commands**: `/forge` (primary), `/forge-cook`.
5. **UI/UX Designer Agent**
   - **Role**: Visual identity and user experience specialist. Ensures "Premium/Wow" aesthetics.
   - **Commands**: `/forge-design`, `/forge-ui-ux`.

### Tier 3: Quality & Integrity (QA)
6. **Tester Agent**
   - **Role**: Verification specialist. Writes TDD suites and ensures high coverage.
   - **Commands**: `/forge-test`, `/forge-web-testing`.
7. **Debugger Agent**
   - **Role**: Forensic bug hunter. Reproduces issues and identifies root causes.
   - **Commands**: `/forge-debug`, `/forge-problem-solving`.
8. **Code Reviewer Agent**
   - **Role**: Quality gatekeeper. Audits security, patterns, and best practices.
   - **Commands**: `/forge-review`, `/code-review`.
9. **Code Simplifier Agent**
   - **Role**: Refactoring specialist. Reduces cyclomatic complexity and cleans logic.
   - **Commands**: `/forge-refactor`, `/forge-clean`.

### Tier 4: Infrastructure & DevOps
10. **Git Manager Agent**
    - **Role**: Version control and repository strategist. Manages branches and merges.
    - **Commands**: `/forge-git`, `/git-*`.
11. **MCP Manager Agent**
    - **Role**: Tool integration and cross-platform bridge specialist.
    - **Commands**: `/forge-mcp-builder`, `/forge-mcp-management`.

### Tier 5: Knowledge & Documentation
12. **Researcher Agent**
    - **Role**: Technical truth seeker. Explores frameworks, libraries, and patterns.
    - **Commands**: `/forge-research`, `/forge-scout`.
13. **Docs Manager Agent**
    - **Role**: Documentation architect. Ensures 1:1 parity between code and docs.
    - **Commands**: `/forge-docs`, `/forge-docs-seeker`.
14. **Journal Agent**
    - **Role**: Historical logger. Records decisions, learnings, and daily updates.
    - **Commands**: `/forge-journal`, `/forge-watzup`.

---

## II. MARKETING KIT (33 Agents)

### Tiers 1-3: Growth Strategy & Content
- **Campaign Manager**: Orchestrates multi-channel launch cycles. `/market-campaign`.
- **Funnel Architect**: Designs customer journeys and conversion points. `/market-funnel`.
- **Copywriter**: High-conversion writing and voice extraction specialist. `/market-write`.
- **Content Creator**: Multi-media asset producer (Blog, Video, Infographics). `/market-content`.
- **Email Wizard**: Sequence and automation flow architect. `/market-email`.
- **Social Media Manager**: Engagement and community presence specialist. `/market-social`.
- **SEO Specialist**: Keyword ranking and technical search authority. `/market-seo`.

### Tiers 4-6: Optimization & Analytics
- **Lead Qualifier**: Prospect scoring and persona fit analysis. `/market-persona`.
- **Analytics Analyst**: Data-driven ROI and attribution specialist. `/market-data-analytics`.
- **Upsell Maximizer**: Expansion revenue and pricing strategist. `/market-pricing`.
- **Continuity Specialist**: Retention and churn reduction specialist. `/market-onboarding`.

### Tiers 7-13: Management & Specialized Ops
- **Brand Manager**: Identity and consistency enforcement. `/market-brand`.
- **Sales Enabler**: Collateral and pitch optimization. `/market-sales`.
- **Community Manager**: User advocacy and event management. `/market-community`.
- **Dashboard Architect**: Real-time KPI visualization specialist. `/market-dashboard`.
- **Marketing Data Architect**: Data pipeline and schema validator. `/market-data-audit`.
- **LTV & Attribution Strategist**: Predictive modeling and attribution specialist. `/market-data-ltv`.
- **MMM Scientist**: Marketing Mix Modeling and budget elasticity expert. `/market-data-mmm`.
- **CDP Manager**: Customer Data Platform and identity resolution leader. `/market-data-cdp`.
- **Revenue Forecaster**: Time-series revenue and churn prediction specialist. `/market-data-revenue`.

### Tiers 14-16: Strategic Deconstruction & Pattern Extraction (Intel)
- **Logic Deconstructor Agent**: Specialized in architectural dismantling and logic recovery. `/market-scout-logic`.
- **Pattern Extractor Agent**: High-fidelity distillation of strategic DNA and competitive patterns. `/market-extract-pattern`.

### Tiers 17-19: Product-Led Growth (PLG) & Product thinking
- **Growth Product Lead**: Feature-adoption and PLG strategist. `/market-product-growth`.
- **Onboarding Experience Designer**: User success and retention architect. `/market-onboarding`.
- **Virality Engineer**: Loop and referral system specialist. `/market-virality`.

---

## III. DEVOPS KIT (12 Agents)

### Tier 1: Infrastructure & State Management
- **Infrastructure Architect**: Cloud strategy and blueprint designer. `/ops-infra-plan`.
- **Caesar Ops Manager (Orchestrator)**: DevOps "Conductor". `/ops-deploy`, `/ops-status`.
- **IaC Specialist (Terraform)**: Immutable infra implementation. `/ops-terraform`.
- **Secrets & Config Manager**: Secure key vault strategy. `/ops-secrets`.

### Tier 2: Deployment & Service Mesh
- **CI/CD Pipeline Engineer**: Automation and build optimization. `/ops-setup-cicd`.
- **Container & K8s Specialist**: K8s, scaling, and service mesh. `/ops-k8s`.
- **Deployment Validator**: Quality gatekeeper for releases. `/ops-validate-deploy`.
- **Canary Manager**: Progressive rollout specialist. `/ops-canary`.

### Tier 3: Observability & Governance
- **Observability Engineer**: Telemetry, logging, and visualization. `/ops-monitoring`.
- **Incident Response Manager**: On-call and forensic leader. `/ops-incident`.
- **SecOps & Compliance Analyst**: Infrastructure hardening. `/ops-audit-infra`.
- **FinOps & Cost Optimizer**: Resource efficiency strategist. `/ops-cost-analysis`.

---

## IV. CROSS-KIT SYNERGY
- **Engineer → Marketing**: Product release announcements and adoption analytics.
- **Marketing → Engineer**: User behavior insights and identified UI/UX friction points.
- **Nexus → All**: Governance, audit, and compliance gates.

## Iron Laws
1. **Zero Orphan**: Every agent must belong to a defined tier and workflow.
2. **Standard Handoff**: Agent-to-agent communication must follow the `forge-orchestration-protocol.md`.
3. **Whitewash Verification**: Agents must never reference Caesar Nexus or external brands.

