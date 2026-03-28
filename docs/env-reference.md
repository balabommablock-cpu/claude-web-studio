# Environment Variables Reference

These are the environment variables the agents will help you configure during setup. This is a reference document, not a starter template.

## Database

| Variable | Service | Notes |
|----------|---------|-------|
| DATABASE_URL | Supabase | Connection string from Supabase dashboard. Uses pooled connection on port 6543. |
| DIRECT_URL | Supabase | Direct connection string on port 5432. Used by Drizzle for migrations. |

## Auth (Clerk)

| Variable | Service | Notes |
|----------|---------|-------|
| NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY | Clerk | Public key from Clerk dashboard > API Keys. Prefixed with `pk_test_` in dev. |
| CLERK_SECRET_KEY | Clerk | Secret key from Clerk dashboard > API Keys. Prefixed with `sk_test_` in dev. |
| NEXT_PUBLIC_CLERK_SIGN_IN_URL | Clerk | Route for sign-in page. Default: `/sign-in` |
| NEXT_PUBLIC_CLERK_SIGN_UP_URL | Clerk | Route for sign-up page. Default: `/sign-up` |
| NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL | Clerk | Redirect after sign-in. Default: `/dashboard` |
| NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL | Clerk | Redirect after sign-up. Default: `/dashboard` |

## Payments (Stripe)

| Variable | Service | Notes |
|----------|---------|-------|
| NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY | Stripe | Public key from Stripe > Developers > API Keys. Prefixed with `pk_test_` in dev. |
| STRIPE_SECRET_KEY | Stripe | Secret key from Stripe > Developers > API Keys. Prefixed with `sk_test_` in dev. |
| STRIPE_WEBHOOK_SECRET | Stripe | Webhook signing secret. Set up endpoint at `/api/webhooks/stripe` in Stripe > Developers > Webhooks. Events: `checkout.session.completed`, `customer.subscription.deleted`, `invoice.payment_failed`. |

## Analytics (PostHog)

| Variable | Service | Notes |
|----------|---------|-------|
| NEXT_PUBLIC_POSTHOG_KEY | PostHog | Client-side project API key from PostHog > Project Settings. |
| NEXT_PUBLIC_POSTHOG_HOST | PostHog | PostHog instance URL. Default: `https://app.posthog.com` |
| POSTHOG_KEY | PostHog | Server-side API key for backend event capture (e.g., Stripe webhook events). |

## Email (Resend)

| Variable | Service | Notes |
|----------|---------|-------|
| RESEND_API_KEY | Resend | API key from Resend dashboard. Prefixed with `re_`. Used for transactional emails (welcome, receipts). |

## Error Tracking (Sentry)

| Variable | Service | Notes |
|----------|---------|-------|
| NEXT_PUBLIC_SENTRY_DSN | Sentry | Client DSN from Sentry > Settings > Client Keys. Used for browser error tracking. |
| SENTRY_AUTH_TOKEN | Sentry | Auth token for source map uploads during build. Create at Sentry > Settings > Auth Tokens. |

## Deployment (Vercel)

| Variable | Service | Notes |
|----------|---------|-------|
| VERCEL_TOKEN | Vercel | Personal access token from Vercel > Settings > Tokens. Used for CI/CD deployments. |

## App Config

| Variable | Service | Notes |
|----------|---------|-------|
| NEXT_PUBLIC_APP_URL | App | Base URL of the application. Use `http://localhost:3000` in dev, your production domain in prod. |
| NEXT_PUBLIC_APP_NAME | App | Display name of your application. Used in meta tags and email templates. |
