# LinKup — Marketplace prototype

This is a responsive, single-page frontend prototype for LinKup, a local services marketplace starting in Red Deer, Alberta. Open `index.html` in a browser to test category navigation, keyword/location search, price filtering, sorting, sample profiles, quote-request UI, sign-in demo, and a provider dashboard preview.

## Important current limitations

This deliverable is a **frontend prototype**, not a production-ready marketplace. Forms deliberately tell users they are in demo mode. There is no real authentication, database persistence, private messaging, live quotes, real reviews, verification workflow, payments, admin backend, or server authorization. Sample providers and images are illustrative and must not be presented as real businesses. No reviews, ratings, or verification badges are fabricated.

## Suggested production stack

- Next.js + TypeScript
- Supabase Auth, Postgres, Row Level Security, and Storage
- Stripe Checkout and signed webhooks for payments
- Server-side authorization for admin and provider actions

## Launch checklist

1. Create a Supabase project and configure environment variables on the server.
2. Add database tables for profiles, providers, categories, listings/photos, quote requests, quotes, conversations/messages, reviews, saved providers, verification records, reports, subscriptions, payments, ads, and platform settings.
3. Enable and test RLS for every table; test with separate customer/provider accounts. Do not let users set their own admin role.
4. Add secure server actions for quote submission, participant-only messaging, review eligibility, report moderation, provider listing changes, and account deletion/export.
5. Add authenticated image upload policies and validation.
6. Add Stripe server-side checkout creation and verify webhook signatures before marking a payment successful. Never trust client-supplied amounts.
7. Build protected admin routes and audit logs; verify permissions on the server.
8. Add real terms/privacy/help pages, rate limiting, spam prevention, backups, accessibility checks, and automated end-to-end tests.
9. Deploy the frontend and backend, configure production domains and authentication redirect URLs, then invite a small group of providers for a pilot.

## Revenue model defaults

The requested $4 CAD listing fee can be a configurable example. Keep free listings enabled in development. Clearly label sponsored results and ads. Only activate paid features after payment is confirmed by the backend.
