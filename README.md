# Claude Web Studio

Your code ships with quality gates you'd normally skip.

A CLAUDE.md configuration for Claude Code that enforces accessibility, security, SEO, legal compliance, and analytics — automatically, while you build. Not after. Not as a review step. Built into every file the agents produce.

---

## The problem

Solo builders skip things. Not because they're lazy — because there's too much to remember. Privacy policy. OWASP audit. OG meta tags. Analytics taxonomy. Accessibility. Error states. Empty states. Loading states. Sitemap. Cookie consent.

You remember 6 of these. You ship without the other 9. Users notice.

## What this does

Drop this CLAUDE.md into any project. Tell Claude Code what you want to build. The orchestrator routes to specialist agents AND enforces quality gates at every step.

- Before any page is complete → accessibility, responsive, SEO checks
- Before any API route is complete → auth, validation, error handling checks
- Before you ship → security audit, legal docs, analytics, performance checks

You build features. Quality happens in the background.

---

## Install

```bash
git clone https://github.com/balabommablock-cpu/claude-web-studio.git .claude-web-studio
cp .claude-web-studio/CLAUDE.md ./CLAUDE.md
cp -r .claude-web-studio/.claude ./.claude
```

Open Claude Code. Start building.

---

## Try it in 60 seconds

After installing, type in Claude Code:

> I want to build a waitlist page for a SaaS that helps freelancers track invoices.

Watch what happens:
1. Orchestrator asks 3 clarifying questions (not 20)
2. Strategy agent runs a quick competitive scan
3. PRD agent writes a minimal spec (saved to docs/prd.md)
4. You approve the spec
5. Frontend + Backend agents build it
6. Quality gates auto-check: accessibility, SEO meta, error states
7. You have a waitlist page with analytics, legal compliance, and SEO — in one session

Not "it writes code." Every AI tool writes code. This one refuses to let you ship without the 15 things you'd normally forget.

---

## Quality gates (enforced automatically)

### Every page
| Check | What |
|-------|------|
| Accessibility | WCAG 2.1 AA — contrast, keyboard, screen reader, focus |
| Responsive | 375px, 768px, 1280px |
| Loading state | Skeleton or spinner |
| Error state | Graceful failure message |
| Empty state | Meaningful content |
| SEO | Meta title, description, OG tags |

### Every API route
| Check | What |
|-------|------|
| Auth | Protected unless explicitly public |
| Validation | All inputs validated and sanitized |
| Error handling | try/catch with HTTP status codes |
| Types | Request/response TypeScript types |

### Before you ship
| Check | What |
|-------|------|
| Security | OWASP top 10 audit |
| Legal | Privacy policy + ToS matching actual data use |
| Analytics | Event taxonomy instrumented |
| Performance | Lighthouse > 90 |
| SEO | Sitemap, robots.txt, structured data |

---

## Slash commands

| Command | What it does |
|---------|-------------|
| `/plan` | Write a spec before building |
| `/build [feature]` | Build end-to-end with quality gates |
| `/ship` | Pre-launch: security, legal, SEO, analytics, performance |
| `/stuck` | Top 3 next moves ranked by impact |
| `/missing` | Gap analysis — what haven't you built? |
| `/blockers` | What stops you from launching TODAY? |
| `/sprint [time]` | Tasks sized to your available time |
| `/teardown` | Devil's Advocate rips apart your plan |
| `/progress` | Visual dashboard across all domains |

---

## Agents under the hood

You don't need to know about these. The orchestrator routes automatically. Quality gates invoke agents silently. You just build.

**Core (auto-invoked):** security, evaluator, seo, legal, accessibility

**Builder:** frontend, backend, design, testing, performance, devops

**Strategic:** strategy, prd, architecture, devils-advocate, pricing, brand, user-research

**Growth:** analytics, marketing, growth, content, community, ux-writing, support, finance, documentation, launch

28 agents total. [See all agent files](.claude/agents/)

---

## Solo Builder Mode

Tell the system you're building alone. It adapts:

- **Revenue-first** — validate willingness to pay before writing code
- **Energy-aware** — "I have 30 minutes" gets different tasks than "4 hours"
- **Decision journal** — every major decision logged with rationale
- **Progress dashboard** — visual blind-spot detector
- **Session memory** — picks up where you left off

---

## Default stack

| Layer | Tech |
|-------|------|
| Framework | Next.js 14 (App Router) |
| Language | TypeScript (strict) |
| Styling | Tailwind CSS |
| Database | Supabase (Postgres) |
| ORM | Drizzle |
| Auth | Clerk |
| Payments | Stripe |
| Analytics | PostHog |
| Deploy | Vercel |
| Testing | Vitest + Playwright |

---

## License

MIT — see [LICENSE](LICENSE)

Built by [Rishabh Balabomma](https://github.com/balabommablock-cpu)
