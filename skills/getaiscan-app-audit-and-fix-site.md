---
name: getaiscan-app-audit-and-fix-site
description: Audit a website's AI visibility with AIScan — triage with the cheap checks, run the full four-score audit, then buy the fix pack or the SKILL.md fix file — paying each step with x402 on Base.
api: openapi/getaiscan-app-openapi.json
operations:
  - index
  - check_health
  - check_llms_txt
  - check_schema
  - check_agent_files
  - check_mcp
  - full_audit
  - fix_pack
  - generate_skill
  - full_report
method: generated
generated: '2026-09-19'
grounding: Every operationId above exists verbatim in openapi/getaiscan-app-openapi.json (5.9.4). Prices are the ones in the free index and the OpenAPI x-payment-info blocks on 2026-09-19; the payment loop is the one observed in the live 402 challenge.
---

# Audit a website's AI visibility and get the fixes

Base URL `https://api.getaiscan.app`. Every capability is `POST /api/agent/{capability}` with a JSON body and an x402 V2 payment. There is no API key and no account. Every call costs real USDC on Base mainnet — there is no sandbox — so read the prices before you start and prefer the cheap checks when you only need one answer.

## 0. Read the catalog (free)

`GET /api/agent/index` (`index`) — no payment. Returns every capability with `price_usdc`, a description and an endpoint template, plus the payment terms. Treat this as the source of truth for prices; the agent card and the descriptors lag it.

## The payment loop (every paid step)

1. `POST /api/agent/{capability}` with `Content-Type: application/json` and the body for that capability.
2. Expect **402**. Read the `PAYMENT-REQUIRED` header (base64 JSON) or the body: `accepts[0]` gives `scheme` (`exact`), `network` (`eip155:8453`), `amount` in USDC base units (6 decimals — `60000` is 0.06 USDC), `asset` (USDC `0x8335…2913`), `payTo` and `maxTimeoutSeconds` (300).
3. Pay one of two ways within 300 seconds: sign an EIP-3009 `transferWithAuthorization` for exactly that amount (the `exact` scheme, settled by the Coinbase CDP facilitator), or send the USDC directly to `payTo` and keep the transaction hash.
4. Retry the **identical** request with `PAYMENT-SIGNATURE: <signed payload or tx hash>`. Use that header name — the older `X-Payment` spelling appears in stale descriptors.
5. A **200** carries the report. There is no idempotency key: if the retry times out after payment, do not blindly re-pay — check your wallet and contact report@getaiscan.app, because nothing published says a tx hash can be re-presented.

## 1. Triage with the cheap checks (0.06-0.08 USDC each)

Body: `{"url": "https://example.com"}` for all five.

- `check_health` (0.06) — availability, robots.txt, AI-crawler access (GPTBot, ClaudeBot, PerplexityBot), sitemap.
- `check_llms_txt` (0.07) — llms.txt existence and quality.
- `check_schema` (0.07) — Schema.org JSON-LD, FAQ and Organization schema.
- `check_agent_files` (0.07) — openapi.json, ai-plugin.json, x402 support.
- `check_mcp` (0.08) — /.well-known/mcp.json, agent.json, MCP server card.

Run only the ones your question needs; all five together cost 0.35 USDC, the same as the full audit.

## 2. Score everything at once

- `full_audit` (0.35) — all four scores (AEO, GEO, Agent Readiness, MCP Readiness) and the 80+ checks behind them. Body `{"url": ...}`.

## 3. Buy the fixes

- `fix_pack` (0.55) — copy-paste fix instructions for every failed check.
- `generate_skill` (0.45) — a ready-to-run SKILL.md that a coding agent executes to apply the fixes. Not in the agent card yet; it is in the index and the OpenAPI.
- `full_report` (1.55) — the bundle: full audit + fix pack + generated llms.txt and mcp.json. Cheaper than buying the parts (0.35 + 0.55 + 0.30 + 0.30 = 1.50 without the skill file) only if you want all of them; otherwise buy the parts.

## Rules that are not in the spec

- The only declared responses are 200 and 402. A wrong capability id returns a 404 JSON object with an `available[]` list; a malformed body has no documented status.
- No rate limits are published; the price is the throttle.
- There is no refund policy published. Assume a paid call that fails is a support conversation (report@getaiscan.app), not an API operation.
