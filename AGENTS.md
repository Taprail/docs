# Documentation project instructions

The public developer docs for **Pay with Taprail** and **Taprail loyalty** — the
merchant-facing API, webhooks, JS SDK, and concepts. Built on
[Mintlify](https://mintlify.com).

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter; configuration lives in `docs.json`
- The API Reference renders from `openapi.json`; each `api-reference/*.mdx` page is a thin
  wrapper that points at one operation. Keep `openapi.json` as the single source of truth
  for request/response shapes — edit it, not hand-written tables, when the contract changes.
- Preview locally with `npx mint dev`; validate navigation and links with
  `npx mint broken-links` before shipping.

## Terminology

- **Pay with Taprail** — the merchant payments product (server API + hosted checkout + SDK).
- **Taprail loyalty** — the cashback product; its unit is a **program** (a cashback rule).
- **merchant** / **partner dashboard** — say "merchant" for the integrating business; the
  dashboard lives at `partner.taprail.app`. Don't say "user" for a merchant.
- **order** — the unit of the merchant API (not "transaction" or "payment"). The create-order
  response is the **intent** you hand to the SDK.
- **the processor** / **the Taprail app** — refer to payment infrastructure generically.
  Never name third-party providers (the backend names exist, but they stay out of the docs).
- Amounts are **kobo** integers (₦1 = 100 kobo); the only currency is **NGN**.

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Monochrome brand only: bone (`#f6f6f4`) on black (`#0a0a0c`) — no accent colors
- Every documented field, status, error code, and sample must come from the real backend
  contract. Don't document aspirational or unreleased behavior.

## Content boundaries

This repo is **public**. Document only the surface a merchant or developer integrates with:

- The `/v1/merchant/*` and `/v1/checkout/*` API, signed webhooks, the `@taprail/checkout`
  JS SDK, and the loyalty product as a merchant-facing concept.

Do **not** document, reference, or hint at internal surface:

- The admin console, partner-dashboard internals, the consumer app's private endpoints,
  reconciler/worker mechanics, or settlement plumbing beyond what a merchant observes.
- Unreleased or review-only verticals (e.g. cards, ambassador/referrals).
- Third-party provider names, internal mechanisms, secrets, or infrastructure.
