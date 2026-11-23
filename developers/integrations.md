---
description: >-
  What works with Lid today: the live stack (Privy, MoonPay, Alchemy, Pinata,
  Solana Pay, USDC), payment inputs, delivery targets, the agent connection, the
  REST API, the SDK, the Pay with Lid button, w
---

# Integrations

Lid is designed to play well with the tools businesses and developers already use. This page covers what integrates today and how to propose a new integration.

## What integrates today

**The live stack**

* **Privy** · embedded wallet and auth. Live.
* **MoonPay** · adding funds by card. Live.
* **Alchemy** · Solana RPC. Live.
* **Pinata** · IPFS metadata storage. Live.
* **Solana Pay** · checkout UX. Live.
* **USDC SPL Token** · settlement asset. Live.

**Payment inputs**

* USDC on Solana (native)
* A card on the buyer side: the buyer adds digital dollars (USDC) by card inside the app, through MoonPay, and pays in USDC

**Delivery targets**

* Direct file delivery (PDF, ZIP, video, any file type)
* URL-based delivery (Notion, Google Drive, YouTube, Discord, Telegram, any link)

**Social sharing**

* Share links are plain URLs, so they work on every platform. X, LinkedIn, Instagram, TikTok, Threads, email, newsletter, Discord, Telegram, community forums, blogs.

**Agent surface**

* The agent connection over MCP, live. Agents build sites, create products, share links, run challenges and read sales. See [Agents on Lid](../agents/).

**Developer surface**

* The REST API at `api.lid.pro/api/v1`, the SDK `@lidpro/sdk` on npm, and the Pay with Lid button, as a script tag or as `@lidpro/pay` for React. Live. See [API, SDK and buy button](agentic-commerce-api.md).

**Webhooks**

* Live. Signed deliveries for `purchase.completed`, `prize.claimed`, `subscription.created` and `bounty.submission.created`. See [Webhooks and events](../agents/webhooks.md).

**Verification**

* Every sale produces a Solana transaction signature that can be verified on any block explorer.

## Integration principles we hold to

**Don't break the trust layer.** No integration is allowed to touch the money flow. External systems read state, receive events, or trigger actions. Settlement stays on-chain.

**Don't expose Web3 complexity.** Any integration Lid endorses must preserve the abstracted UX. If an integration adds wallet prompts or chain selectors to the end-user flow, it's not on-brand.

**Don't add hidden fees.** Integration partners can charge their own fees visibly, on top of Lid. They cannot skim Lid's 3% or take commission from the seller's share without explicit disclosure.

## Proposing an integration

If you want to integrate Lid with a product you're building, we want to hear from you. Especially if you're building:

* AI agent frameworks
* Creator toolkits (content platforms, newsletter tools, community platforms)
* Analytics or attribution tools
* Marketplaces or aggregators
* Crypto wallets or exchanges

Email [hello@lid.pro](mailto:hello@lid.pro) with:

1. What you're building
2. How you'd integrate Lid
3. What API or event surface you'd need
4. Timeline

## Partnership posture

We do not do prestige partnerships for the sake of prestige. Every integration we endorse has to produce measurable benefit for sellers or sharers. Big-partnership theater gets filtered out.

Lightweight, practical, measurable. That's the standard.

Next: [Vision](../company/vision.md)
