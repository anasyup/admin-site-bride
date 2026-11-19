# Admin Site Bride — HUSHAE Backend

Complete backend for the **HUSHAE / Admin Site Bride** project — an Express + Mongoose (MongoDB) ecommerce backend designed for **Vercel serverless** deployment.

**Stack:** Node.js · Express · Mongoose · MongoDB Atlas (or embedded in-memory for local dev) · Vercel serverless (`api/index.js`)

## Layout

```
api/index.js          Vercel serverless entry — exports the Express app as handler
src/app.js            Express app wiring (middleware, routes mounting)
src/server.js         Local dev server
src/config.js         Environment configuration
src/models/           60+ Mongoose models (Order, Product, Theme, CmsPage, …)
src/routes/           50+ route modules (auth, products, orders, payments, theme, …)
src/middleware/       Auth, rate-limit, sanitize
src/utils/            Order flow, promotion engine, inventory engine, mailer, …
src/seed/             Database seed scripts
scripts/, test-*.js   Finance PnL script + test suites
HUSHAE-BACKEND-COMPLETE.txt   Entire backend concatenated into one reference file
.env.example          Local env template (live secrets stay on Vercel only)
```

## Run locally

```bash
cp .env.example .env   # edit values
npm install
npm run dev
```

## Deploy (Vercel)

Repo root must contain a `vercel.json` with rewrites `/api/* → /api` and `/(.*) → /index.html` (SPA), plus this backend installed from `backend/`. Secrets (`MONGODB_URI`, `JWT_SECRET`, admin credentials, SMTP/Twilio keys) are configured in Vercel project settings — never committed.

## Notes

- No frontend code lives here.
- The single-file dump `HUSHAE-BACKEND-COMPLETE.txt` is for review/reading; the folder tree is the runnable project.
- Generated from the HUSHAE production repository (`hushae/backend/`), branch `main`.
