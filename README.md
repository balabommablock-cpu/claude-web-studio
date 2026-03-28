# Claude Web Studio

Build and launch a complete web business — from brand identity to production deployment — using 28 specialist AI agents in Claude Code.

Strategy. Design. Engineering. SEO. Analytics. Marketing. Legal. Security. Growth. Monetization. Every domain a solo builder needs, covered by a dedicated agent.

---

## Why This Exists

Building a web product alone means being the PM, designer, engineer, marketer, lawyer, and growth lead — simultaneously. Most frameworks give you code generation. This gives you the entire company.

**The orchestration problem solved:** Multi-agent systems fail because the orchestrator does everything itself. Claude Web Studio uses **Negative Permissions** — the orchestrator is explicitly prohibited from writing code, copy, or strategy. It can only route to specialist agents. This is why agents actually get invoked.

---

## Quick Start

```bash
# Clone into your project directory
git clone https://github.com/balabommablock-cpu/claude-web-studio.git .studio
cp .studio/CLAUDE.md ./CLAUDE.md
cp -r .studio/agents ./agents

# Open Claude Code and start
claude
```

Then type what you want to build. The orchestrator handles the rest.

---

## Slash Commands

| Command | What it does |
|---------|-------------|
| `/plan` | Write a spec before building anything |
| `/build [feature]` | Build a feature end-to-end |
| `/ship` | Pre-launch checklist → compliance → SEO → deploy |
| `/stuck` | "What should I do next?" — top 3 moves by impact |
| `/missing` | Gap analysis — what haven't you built yet? |
| `/blockers` | What stops you from launching TODAY? |
| `/sprint [time]` | "I have 2 hours" — sized task list |
| `/teardown` | Devil's Advocate rips apart your plan |
| `/progress` | Visual dashboard across all domains |

---

## Solo Builder Mode

When you tell the system you're building alone, it activates:

- **Revenue-first ordering** — validate willingness to pay before writing code
- **Energy-aware routing** — "I have 30 minutes" gets different tasks than "I have 4 hours"
- **Decision journal** — every major decision logged with rationale (so you don't relitigate)
- **Progress dashboard** — visual blind-spot detector across all domains
- **Session memory** — picks up where you left off, even weeks later

---

## 28 Specialist Agents

### Strategy & Research
| Agent | Handles |
|-------|---------|
| Strategy | Market research, ICP, positioning, competitive analysis |
| PRD | Requirements, user flows, acceptance criteria |
| Architecture | Tech stack, system design, database schema, API design |
| User Research | Interview guides, validation, journey mapping, synthesis |
| Brand Identity | Name, voice, tone, visual direction, tagline, values |
| Pricing Strategy | WTP research, tier design, free/paid line, A/B testing |

### Design & Content
| Agent | Handles |
|-------|---------|
| Design | UI/UX, design system, responsive, accessibility |
| UX Writing | Onboarding copy, error messages, empty states, tooltips |
| Content Strategy | Blog calendar, SEO articles, help center, tutorials |
| Community | Discord/Slack strategy, moderation, UGC, ambassadors |

### Engineering
| Agent | Handles |
|-------|---------|
| Frontend | Next.js App Router, React, TypeScript, Tailwind |
| Backend | API routes, Drizzle ORM, auth, Stripe integration |
| DevOps | Vercel, CI/CD, monitoring, environment management |
| Performance | Core Web Vitals, bundle optimization, caching |
| Security | OWASP top 10, auth hardening, CSP, dependency audit |

### Growth & Launch
| Agent | Handles |
|-------|---------|
| SEO | Technical SEO, structured data, sitemap, meta tags |
| Analytics | PostHog/Mixpanel, event taxonomy, funnels, attribution |
| Marketing | Landing pages, email sequences, social, launch strategy |
| Growth | Retention, referrals, activation optimization |
| Financial Modeling | CAC, LTV, burn rate, runway, break-even |

### Operations
| Agent | Handles |
|-------|---------|
| Testing | Vitest, Playwright, coverage thresholds |
| Legal | Privacy policy, ToS, cookie consent, GDPR |
| Customer Support | Help center, FAQ, chatbot flows, escalation |
| Documentation | API docs, user guides, changelog |
| Launch | Pre-launch checklist, staged rollout, post-launch monitoring |

### Meta-Agents
| Agent | Handles |
|-------|---------|
| Evaluator | Quality gates at every phase, self-critique enforcement, retry limits |
| Devil's Advocate | Challenges strategy, pricing, architecture — runs pre-mortems |

---

## How It Works

```
You: "I want to build a SaaS for freelancer invoicing"

Orchestrator detects: new project, solo builder
  → Strategy agent: market sizing, ICP, competitive landscape
  → Pricing agent: willingness to pay analysis
  → Devil's Advocate: "Why not use Wave/FreshBooks?"
  → GATE: User confirms direction

  → PRD agent: feature spec with acceptance criteria
  → Architecture agent: Next.js + Supabase + Stripe + Clerk
  → Design agent: UI spec, design system tokens, component library
  → Frontend agent: implements screens
  → Backend agent: API routes, database schema, auth, payments
  → Testing agent: unit + E2E tests

  → SEO agent: meta tags, structured data, sitemap
  → Analytics agent: event taxonomy, funnels
  → Legal agent: privacy policy, ToS
  → Marketing agent: landing page copy, launch email
  → Launch agent: deploy to Vercel, staged rollout

Every agent writes to disk. Every decision logged. Every phase gate enforced.
```

---

## vs. Doing It Yourself

| Domain | Without Claude Web Studio | With Claude Web Studio |
|--------|--------------------------|----------------------|
| Strategy | Skip it, build what feels right | Market-validated direction before code |
| Design | Copy a template, hope it works | Platform-native design system with accessibility |
| Engineering | You write everything | Agent writes, you review |
| SEO | Add meta tags after launch (too late) | Built into every page from day 1 |
| Legal | Copy a privacy policy from the internet | Customized to your actual data practices |
| Analytics | Add Google Analytics, never check it | Event taxonomy designed for your business metrics |
| Security | "It's probably fine" | OWASP top 10 audit before launch |
| Growth | Post on Twitter, hope for the best | Structured acquisition, activation, retention |

---

## Tech Stack (Default)

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 14 (App Router) |
| Language | TypeScript (strict mode) |
| Styling | Tailwind CSS |
| Database | Supabase (Postgres) |
| ORM | Drizzle |
| Auth | Clerk |
| Payments | Stripe |
| Analytics | PostHog |
| Deployment | Vercel |
| Testing | Vitest + Playwright |

The Architecture agent can recommend alternatives based on your requirements.

---

## License

MIT — build whatever you want.

Built by [Rishabh Balabomma](https://github.com/balabommablock-cpu) | [LinkedIn](https://www.linkedin.com/in/brishabhrao/)
