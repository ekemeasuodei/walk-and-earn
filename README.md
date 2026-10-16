# Walk & Earn — Version 2 blueprint

This is a navigable front-end planning prototype for:
- overview and demo step counter
- account screen preview
- sponsor enquiry preview
- draft reward rules
- admin dashboard preview

It does NOT include real accounts, a server, secure step verification, a database, sponsor payments, or cash withdrawals. Do not enter real passwords or bank details. Do not advertise cash earnings from this demo.

## Publish this prototype
1. Upload `index.html` to a GitHub repository.
2. Open repository Settings → Pages.
3. Choose deploy from a branch, branch `main`, folder `/(root)`, and save.
4. Open the Pages URL shown by GitHub.
5. Test on Android and desktop.

## Production architecture recommended
- Front end: responsive PWA; later consider React Native/Expo or another mobile app framework.
- Authentication/database: Supabase Auth + Postgres.
- Security: enable Row Level Security (RLS) on every exposed table; test read/write policies. Never expose service-role keys in client code.
- Backend: server-side functions for reward calculation, campaign budget reservation, withdrawal approval and payment-provider webhooks.
- Payouts: apply with a provider, confirm eligibility and terms for the business model, and start in test mode.
- Sponsors: signed campaign terms, actual funds received, reward budget reserve, caps, expiry and reconciliation.
- Compliance: privacy notice, terms, country-specific rules, user support, tax/accounting and legal review.

## Minimum database tables to design
profiles, step_summaries, campaigns, sponsor_funds, reward_ledger, withdrawal_requests, payout_events, fraud_reviews, admin_audit_log.

Suggested reward ledger states: pending, approved, reserved, paid, failed, reversed.
