---
name: getaiscan-app-compare-competitors
description: Run an AIScan gap analysis of one website against a competitor's — who wins each AI-visibility category and why — as a single paid x402 call.
api: openapi/getaiscan-app-openapi.json
operations:
  - index
  - compare
  - full_audit
method: generated
generated: '2026-09-19'
grounding: Every operationId above exists verbatim in openapi/getaiscan-app-openapi.json (5.9.4). The compare body fields (url, competitor) are the ones the contract declares.
---

# Compare a site against a competitor

## 1. Confirm the price (free)

`GET /api/agent/index` (`index`) — `compare` was 0.80 USDC on 2026-09-19.

## 2. Run the comparison (0.80 USDC)

`POST /api/agent/compare` (`compare`) with body:

```json
{"url": "https://yoursite.example", "competitor": "https://rival.example"}
```

Both fields are required and both must be full URLs; the contract's `x-guidance` says so explicitly ("compare needs both url and competitor in the JSON body"). Follow the x402 payment loop from `getaiscan-app-audit-and-fix-site`: expect 402, pay `accepts[0].amount` (800000 base units) to `payTo` on Base within 300 seconds, retry with `PAYMENT-SIGNATURE`.

## 3. Go deeper on one side if needed

`full_audit` (0.35) on whichever URL lost a category gives the 80+ underlying checks; `compare` reports who wins each category and why, not every check.

## Rules

- One call, one payment, one competitor. To compare against several rivals, call `compare` once per rival (0.80 each) — there is no batch form.
- No idempotency key: a retry after an ambiguous outcome is a second payment.
- Nothing is stored; the comparison is returned in-band and must be kept by the caller.
