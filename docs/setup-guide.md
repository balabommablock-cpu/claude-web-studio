# Setup Guide — From Zero to Running in 15 Minutes

This guide walks you through everything you need to go from "I have an idea" to "Claude is building it."

---

## Prerequisites

- **Claude Code** installed ([download](https://claude.ai/claude-code))
- **Node.js 20+** installed (`node --version` to check)
- **Git** installed (`git --version` to check)
- A **GitHub** account
- A credit card for service signups (most have generous free tiers)

---

## Step 1: Create Your Project

```bash
# Create a new directory for your project
mkdir my-saas-app
cd my-saas-app

# Initialize git
git init

# Create a GitHub repo
gh repo create my-saas-app --public --source . --push
```

---

## Step 2: Install Claude Web Studio

```bash
# Clone the framework
git clone https://github.com/balabommablock-cpu/claude-web-studio.git .studio

# Copy the orchestrator and agents into your project
cp .studio/CLAUDE.md ./CLAUDE.md
cp -r .studio/agents ./agents
cp .studio/.env.example ./.env.example

# Clean up
rm -rf .studio

# Create your local env file
cp .env.example .env.local
```

---

## Step 3: Set Up Supabase (Database)

1. Go to [supabase.com](https://supabase.com) and create a free account
2. Click **New Project**
3. Choose a name, password, and region (pick the closest to your users)
4. Wait for the project to provision (~2 minutes)
5. Go to **Settings → Database → Connection String**
6. Copy the **URI** (with your password filled in)

Add to `.env.local`:
```
DATABASE_URL=postgresql://postgres.[your-ref]:[your-password]@aws-0-us-east-1.pooler.supabase.com:6543/postgres
DIRECT_URL=postgresql://postgres.[your-ref]:[your-password]@aws-0-us-east-1.pooler.supabase.com:5432/postgres
```

---

## Step 4: Set Up Clerk (Authentication)

1. Go to [clerk.com](https://clerk.com) and create a free account
2. Click **Create Application**
3. Choose sign-in methods (Email + Google recommended)
4. Go to **API Keys**

Add to `.env.local`:
```
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_...
CLERK_SECRET_KEY=sk_test_...
```

---

## Step 5: Set Up Stripe (Payments)

1. Go to [stripe.com](https://stripe.com) and create an account
2. Stay in **Test Mode** (toggle at top)
3. Go to **Developers → API Keys**

Add to `.env.local`:
```
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_...
STRIPE_SECRET_KEY=sk_test_...
```

Set up webhooks later when you have a deployed URL.

---

## Step 6: Set Up PostHog (Analytics)

1. Go to [posthog.com](https://posthog.com) and create a free account
2. Go to **Project Settings**
3. Copy the **Project API Key**

Add to `.env.local`:
```
NEXT_PUBLIC_POSTHOG_KEY=phc_...
NEXT_PUBLIC_POSTHOG_HOST=https://app.posthog.com
```

---

## Step 7: Set Up Resend (Email)

1. Go to [resend.com](https://resend.com) and create a free account
2. Go to **API Keys** and create one

Add to `.env.local`:
```
RESEND_API_KEY=re_...
```

---

## Step 8: Set Up Vercel (Deployment)

1. Go to [vercel.com](https://vercel.com) and sign in with GitHub
2. Go to **Settings → Tokens** and create a token

Add to `.env.local`:
```
VERCEL_TOKEN=...
```

Later, when your app is built:
```bash
# Deploy to Vercel
npx vercel --prod
```

---

## Step 9: Connect Your Domain (Later)

After your first deploy to Vercel:
1. Go to your Vercel project → **Settings → Domains**
2. Add your domain
3. Update DNS records at your registrar (Vercel shows the exact records)
4. Update `.env.local`:
```
NEXT_PUBLIC_APP_URL=https://yourdomain.com
```

---

## Step 10: Start Building

Open Claude Code in your project directory:

```bash
claude
```

Claude will read the `CLAUDE.md` orchestrator and greet you:

```
Claude Web Studio — ready.

What are you building? Tell me:
1. What it does
2. Who it's for
3. Where you are now
```

**Type your idea and the agents take over.**

---

## Example First Prompts

**From scratch:**
```
I want to build a SaaS tool that helps freelance designers
track their client invoices and get paid faster. Target:
solo designers making $50-200K/year. Starting from scratch.
```

**If you already know what you want:**
```
Build a Next.js 14 app with Clerk auth, Supabase database,
and Stripe subscriptions. I need a dashboard where users can
create and manage invoices.
```

**To explore before building:**
```
I have an idea for a tool in the legal tech space. Help me
validate whether there's a market before I start building.
```

---

## What Happens Next

The orchestrator will map your request to the right agents:

1. **Strategy agent** researches your market and competition
2. **PRD agent** writes requirements from the strategy
3. **Brand Identity agent** creates your brand voice and visual direction
4. **Architecture agent** designs the tech stack
5. **Design agent** creates the design system
6. **Frontend + Backend agents** build the app
7. **SEO, Analytics, Marketing agents** prepare for launch
8. **Launch agent** manages the launch day

All outputs are saved to `docs/` so nothing gets lost between sessions.

---

## Troubleshooting

**"Database connection failed"**
→ Check `DATABASE_URL` in `.env.local` — make sure the password is correct and the Supabase project is running.

**"Clerk: Invalid API key"**
→ Make sure you're using the correct environment (test vs production) keys.

**"Module not found"**
→ Run `npm install` after the Frontend agent creates `package.json`.

**"Port 3000 already in use"**
→ Kill the existing process: `npx kill-port 3000` or use a different port: `npm run dev -- -p 3001`

**"Agent not invoked / Claude doing everything itself"**
→ The CLAUDE.md orchestrator is configured to prevent this. If it happens, say: "Stop. Use the agent routing table. Which agent should handle this?"
