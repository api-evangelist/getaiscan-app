---
name: getaiscan-app-measure-brand-visibility
description: Measure how often AI assistants actually name a brand across 30 niche prompts with AIScan, then buy the fix pack for the weak spots or a head-to-head against a competitor brand — all paid with x402.
api: openapi/getaiscan-app-openapi.json
operations:
  - index
  - visibility_check
  - visibility_fix_pack
  - visibility_vs_competitor
method: generated
generated: '2026-09-19'
grounding: Every operationId above exists verbatim in openapi/getaiscan-app-openapi.json (5.9.4). Body fields (brand, niche, competitor_brand, weak_spots) and the weak_spots hand-off are quoted from the contract's x-guidance.
---

# Measure and fix a brand's visibility in AI answers

These three capabilities take a **brand and a niche**, not a URL. They are the most expensive calls on the surface (1.25-3.50 USDC) because each one runs 30 prompts through a frontier model.

## 1. Confirm prices (free)

`GET /api/agent/index` (`index`).

## 2. Measure (1.95 USDC)

`POST /api/agent/visibility_check` (`visibility_check`) with:

```json
{"brand": "Acme Analytics", "niche": "product analytics for SaaS"}
```

Returns mention rate, share of voice against every competitor the model named, sample mentions, a summary, recommendations — and a `weak_spots` array. Keep `weak_spots`: the contract says "the weak_spots field is included in every visibility_check response" and step 3 needs it verbatim.

## 3. Fix the weak spots (1.25 USDC)

`POST /api/agent/visibility_fix_pack` (`visibility_fix_pack`) with:

```json
{"brand": "Acme Analytics", "niche": "product analytics for SaaS", "weak_spots": [ ...from step 2... ]}
```

Returns ready-to-deploy citable passages, FAQ schema JSON-LD and llms.txt sections for the weakest areas. Do not invent `weak_spots`; the fix pack is generated from them.

## 4. Optional head-to-head (3.50 USDC)

`POST /api/agent/visibility_vs_competitor` (`visibility_vs_competitor`) with `brand`, `competitor_brand` and `niche`. Both brands are measured on the same 30 answers; the response carries both mention rates, share of voice and a verdict. Run it only when a single-brand measurement is not enough — it is nearly twice the price of `visibility_check`.

## Payment and retry rules

Same x402 loop as the other skills: 402 → pay `accepts[0].amount` (1950000 / 1250000 / 3500000 base units) to `payTo` on Base within 300 seconds → retry with `PAYMENT-SIGNATURE`. No idempotency key exists and no refund policy is published, so treat a post-payment timeout as a support conversation (report@getaiscan.app) rather than an automatic retry.
