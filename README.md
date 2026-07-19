# Oblea API docs

Mintlify documentation for [`oblea-backend`](https://github.com/obleaaiteam-create/ObleaAI) — the REST API that turns inbound quote requests into ready-to-review quotations.

`docs.json` lives at the repository **root**, so Mintlify needs no subdirectory setting.

## Preview locally

```bash
npm i -g mint
mint dev          # → http://localhost:3000
```

## Structure

```
.
├── docs.json                 ← navigation, theme, logo
├── introduction.mdx          ← landing page
├── authentication.mdx        ← Supabase JWT vs. internal webhooks
├── errors.mdx                ← status codes
├── concepts/
│   ├── quotation-lifecycle.mdx   ← one email → a READY TO REVIEW quotation
│   └── data-model.mdx            ← the 8 tables + ERD
├── integrations/             ← forwarding email addresses (GET/POST/DELETE)
├── inbox/                    ← stored messages (GET)
├── quotations/              ← quotations (GET/POST + agent draft)
└── webhooks/                ← inbound.new ingress
```

## Publishing

Connected to Mintlify via the GitHub App. Every push to `main` redeploys the site.

## Keeping it accurate

Contracts are written by hand against `oblea-backend/app`. When an endpoint's request or response shape changes, update the matching `.mdx` page (routers live in `oblea-backend/app/routers`, their logic in `oblea-backend/app/services`).
