# Trust Chain Broker

A mobile-first broker dashboard with Clerk email/password authentication and a protected admin control room.

## What is included

- User sign-in and account creation with Clerk
- Portfolio dashboard with deposit and withdrawal flows
- Protected `/admin` page
- Admin user search, account status, suspend, and reactivate controls
- Portable environment template in `.env.example`
- The original approved dashboard mockup and API workspace

## Run on another platform

1. Install Node.js 20+ and pnpm.
2. Copy `.env.example` to `.env`.
3. Create a Clerk application and set `VITE_CLERK_PUBLISHABLE_KEY` and `CLERK_SECRET_KEY`.
4. Set `ADMIN_EMAILS` to the exact email address that should manage users.
5. Install dependencies with `pnpm install`.
6. Run the frontend with `pnpm --filter @workspace/trust-chain-broker run dev`.
7. Run the API with `pnpm --filter @workspace/api-server run dev`.

The password is never stored in this repository. Create or change it through the Clerk sign-up/sign-in screen.

## Admin access

After creating the account with an email listed in `ADMIN_EMAILS`, open `/admin`. Non-admin signed-in users receive a protected access error, and the API enforces the same rule server-side.

## Environment notes

The Replit-managed Clerk keys are injected into this workspace automatically. When moving the project elsewhere, add equivalent Clerk keys in that platform's secret/environment manager; do not commit them to the ZIP or repository.