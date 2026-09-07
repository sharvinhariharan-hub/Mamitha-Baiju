# Website Factory — Master Specification

## Mission
Build a reusable AI-operated website factory. A user should eventually provide only:
1. Domain name
2. Domain registrar/platform
3. Website/web-app requirements and visual direction

The system should discover the environment, plan the build, implement the site, test it, deploy it, connect the domain, verify production, and report completion. Human approval must be required for destructive, paid, security-sensitive, or irreversible actions.

## Initial Project
The first generated website is Mamitha Baiju and must remain in this repository: `sharvinhariharan-hub/Mamitha-Baiju`.

## Agent Roles
- Claude: orchestrator/technical lead and source of architectural decisions.
- Cursor: primary engineering workspace and implementation manager.
- UI agent: frontend/UI/UX specialist.
- Supabase: backend infrastructure when the project requires database, auth, storage, or server functionality. Do not add unnecessary backend infrastructure.
- Kimi: deployment/DevOps assistant; actual hosting provider is selected explicitly by the architecture.
- GitHub: source of truth and version history.
- Cloudflare: domain/DNS/CDN/SSL layer where appropriate.

## Operating Principles
- Do not generate code until requirements and architecture are understood.
- Prefer the simplest architecture that satisfies requirements.
- Never expose or store passwords, API keys, or access tokens in source control.
- Require explicit approval before domain transfer, deleting data, spending money, changing billing, or other irreversible actions.
- Every major change must be reviewable and reversible through Git.
- Agents must document assumptions and blockers.
- Production deployment requires automated checks and a final production verification.

## Factory Pipeline
1. Intake: domain, registrar, requirements, visual direction, assets, constraints.
2. Discovery: identify registrar/DNS/hosting state and available integrations.
3. Planning: produce product requirements, sitemap, architecture, data model, deployment plan, and acceptance criteria.
4. Design: establish visual system and responsive UX.
5. Build: implement frontend and only-required backend capabilities.
6. QA: functional, visual, responsive, accessibility, security, and performance checks.
7. Deploy: build, environment configuration, hosting, DNS, SSL.
8. Verify: production URL, routes, forms/APIs, console errors, mobile/desktop smoke tests.
9. Report: provide URL, deployment state, changes, remaining warnings, and rollback information.

## Registrar Adapter Architecture
Future integrations should be isolated behind adapters, e.g. `HostingerAdapter`, `GoDaddyAdapter`, etc. The orchestrator selects an adapter from the declared registrar. Unsupported registrars must produce a clear manual-action checklist rather than pretending automation succeeded.

## First Milestone
Create the planning/orchestration foundation and project documentation before implementing the actual Mamitha Baiju website. The website itself should be built only after the user supplies/approves its product and visual brief.
