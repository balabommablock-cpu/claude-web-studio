# Claude Web Studio

Build web products from idea to launched business — with specialized AI agents for every step.

Not just code. The full stack: product strategy, design, frontend, backend, SEO, analytics, marketing, security, legal, and growth. Every domain has an expert agent. The orchestrator routes between them automatically.

---

## The Problem This Solves

Most AI-assisted development stops at the code. But shipping a product is:

- Strategy (is this a real market?)
- Product (what exactly should it do?)
- Design (how should it look and feel?)
- Engineering (how does it actually work?)
- SEO (how do people find it?)
- Analytics (how do you know it's working?)
- Marketing (how do you acquire users?)
- Security (is it safe?)
- Legal (are you covered?)
- Growth (how do you keep them?)

This framework covers all of it.

**The other problem:** Multi-agent systems almost always fail because the orchestrator does everything itself instead of invoking specialist agents. Claude Web Studio solves this with a strict orchestration model where the master orchestrator is **prohibited** from writing code, copy, or strategy directly — it can only route to agents.

---

## Installation

```bash
# In your project directory (or an empty directory for a new project):
git clone https://github.com/balabommablock-cpu/claude-web-studio.git .studio
cp .studio/CLAUDE.md ./CLAUDE.md
cp -r .studio/agents ./agents
```

Then open Claude Code in your project directory and start typing.

---

## Usage

**Start a new product:**
```
I want to build [your idea].
```

**Pick up an existing product:**
```
I'm working on [your product]. I need to [add feature / fix / launch / improve SEO].
```

**Jump to a specific phase:**
```
Skip to [marketing / launch / growth / legal] phase.
```

That's it. The orchestrator routes your request to the right agents automatically.

---

## What Gets Built

### Phase 0 — Validate
Strategy agent produces:
- Market sizing (TAM/SAM/SOM with bottom-up math)
- ICP definition (specific, not "everyone")
- Competitive analysis (feature matrix, pricing, weaknesses)
- Positioning statement
- Go-to-market sequence

### Phase 1 — Define
PRD agent produces:
- User stories with acceptance criteria (Given/When/Then)
- MVP scope (defended line between v1 and later)
- Functional requirements (specific system behavior)
- Non-functional requirements (performance, security, accessibility)
- Edge cases and error states

### Phase 2 — Design
Design agent produces:
- Design system (typography, color, spacing, shadows)
- Component library specification
- Dark mode system
- Responsive breakpoint behavior
- Animation and motion guidelines

### Phase 3 — Architect
Architecture agent produces:
- Tech stack recommendation with tradeoffs
- System architecture diagram
- Database schema (with indexes)
- API contract (every endpoint)
- Security model
- Scalability analysis

### Phase 4 — Build
Frontend + Backend agents produce:
- Complete Next.js 14 App Router application
- TypeScript strict mode throughout
- Server Components by default, Client Components where needed
- Stripe integration (checkout, webhooks, portal)
- Auth (Clerk/Auth.js)
- Email (Resend)
- Background jobs (BullMQ)

### Phase 5 — Harden
Security + Accessibility agents produce:
- OWASP Top 10 audit with fixes
- Dependency vulnerability scan (CI/CD)
- WCAG 2.2 AA compliance report
- Automated a11y testing setup

### Phase 6-7 — Test + Optimize
Testing + Performance agents produce:
- Unit tests (Vitest, >80% coverage on critical paths)
- Integration tests (API contracts)
- E2E tests (Playwright, critical user flows)
- Core Web Vitals passing (LCP <2.5s, CLS <0.1, INP <200ms)

### Phase 8 — Find
SEO agent produces:
- Technical SEO foundation (robots.txt, sitemap, canonicals)
- Metadata implementation (Next.js 14 Metadata API)
- Structured data (JSON-LD for every content type)
- Core Web Vitals optimization guide
- Keyword strategy (tiered by intent)

### Phase 9 — Measure
Analytics agent produces:
- Tracking plan (every event with properties and business question)
- PostHog/GA4 implementation (server + client)
- Conversion funnel setup
- Dashboard requirements (daily health, activation, retention, revenue)
- Automated alerts configuration

### Phase 10 — Legalize
Legal agent produces:
- Privacy Policy (GDPR + CCPA compliant)
- Terms of Service
- Cookie Policy + consent implementation (code-ready)
- GDPR implementation checklist

### Phase 11 — Market
Marketing agent produces:
- Landing page copy (headline through FAQ)
- Email sequences (welcome, onboarding D1/D3/D7, nurture, win-back)
- Twitter/X launch thread
- LinkedIn post
- Product Hunt assets and first comment

### Phase 12 — Document
Documentation agent produces:
- OpenAPI spec for all endpoints
- User-facing help docs
- Developer onboarding guide
- Architecture Decision Records (ADRs)

### Phase 13 — Ship
DevOps agent produces:
- GitHub Actions CI/CD (lint → test → staging → E2E → production)
- Vercel/Railway deployment config
- Environment variable management
- Monitoring setup (Sentry + uptime)
- Backup strategy
- Incident response runbook

### Phase 14 — Launch
Launch agent produces:
- Pre-launch checklist (70+ items)
- Launch day timeline (hour by hour)
- Product Hunt submission
- HN Show HN post
- Press release

### Phase 15 — Grow
Growth agent produces:
- Activation funnel optimization
- Retention mechanics (habit loops, notifications)
- Referral program design (double-sided, tracked)
- Upgrade trigger design
- Churn prevention (exit survey, prediction signals)
- Experiment framework (ICE scoring, A/B test setup)

---

## Agent Architecture

28 specialist agents, each with:
- Strict scope (what they own and don't own)
- Required inputs (what context they need)
- Specific deliverables (exact artifacts)
- Quality gates (measurable, not vague)
- Anti-patterns (what they never do)
- Tool preferences (specific libraries, not generic advice)
- Handoff protocol (what they pass to the next agent)

The orchestrator (`CLAUDE.md`) routes between agents with:
- Negative permissions (explicit list of what the orchestrator cannot produce)
- Mandatory invocation rule (every work request invokes at least one agent)
- Artifact persistence (all outputs written to `docs/`)
- Directory isolation (each agent owns specific file paths)
- Review cycles (Testing reviews Frontend, Security reviews Backend)
- Phase gates (structured sign-off before phase transitions)

---

## Tech Stack Defaults

Frontend: Next.js 14 (App Router), TypeScript strict, Tailwind CSS, shadcn/ui
Backend: Next.js API routes (Server Actions for mutations), Drizzle ORM
Database: PostgreSQL (Neon for serverless)
Auth: Clerk
Payments: Stripe
Email: Resend
Analytics: PostHog + GA4
Error tracking: Sentry
Deployment: Vercel
CI/CD: GitHub Actions

All defaults are overridable — tell the Architecture agent your constraints.

---

## License

MIT — use this to build whatever you want.

Built by [Rishabh Balabomma](https://github.com/balabommablock-cpu) | [LinkedIn](https://www.linkedin.com/in/brishabhrao/)
