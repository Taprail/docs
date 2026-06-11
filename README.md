# Taprail developer docs

Public documentation for the **Pay with Taprail** merchant integration — API reference,
webhooks, and the JS SDK. Built with [Mintlify](https://mintlify.com).

## Local preview

```bash
npx mint dev
```

Opens at `http://localhost:3000`. `npx mint broken-links` validates navigation and links.

## Layout

- `docs.json` — site config + navigation
- `index.mdx`, `quickstart.mdx`, `authentication.mdx`, `environments.mdx` — getting started
- `checkout-flows.mdx`, `sdk/` — checkout + SDK guides
- `webhooks/` — events, delivery/retries, signature verification
- `api-reference/` — one page per endpoint
- `errors.mdx` — error codes + retry guidance

## Conventions

- Every documented field and sample comes from the backend contract — don't document
  aspirational behavior. Amounts are kobo integers; the only currency is `NGN`.
- Vendor-neutral copy: say "the processor", never name third-party providers.
- Monochrome brand: bone (`#f6f6f4`) on black (`#0a0a0c`) — no accent colors.
