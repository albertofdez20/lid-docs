---
description: >-
  What integrates with Lid today (Privy, MoonPay, Alchemy, Pinata, Solana Pay,
  USDC, webhooks, MCP), what is being built, and how to propose an integration.
---

# Integrations

Lid is designed to play well with the tools creators and developers already use. This page covers what integrates today, what's planned, and how to propose a new one.

## What integrates today

**The live stack**

* **Privy** · embedded wallet and auth. Live.
* **Alchemy** · Solana RPC. Live.
* **Pinata** · IPFS metadata storage. Live.
* **Solana Pay** · checkout UX. Live.
* **USDC SPL Token** · settlement asset. Live.
* **MoonPay** · card in: card, Apple Pay or bank transfer into digital dollars. Live.
* **Bridge** · bank out. Being built.
* **Helius webhooks** · transaction monitoring. Planned.
* **x402 / ACP** · long-term horizon.

**Payment inputs**

* USDC on Solana (native)
* Card, Apple Pay or bank transfer on the buyer side, through MoonPay where MoonPay operates: the buyer adds digital dollars (USDC) and pays in USDC

**Delivery targets**

* Direct file delivery (PDF, ZIP, video, any file type)
* URL-based delivery (Notion, Google Drive, YouTube, Discord, Telegram, any link)

**Social sharing**

* Share links are plain URLs, so they work on every platform. X, LinkedIn, Instagram, TikTok, Threads, email, newsletter, Discord, Telegram, community forums, blogs.

**Agent surface**

* The agent connection over MCP, live. Agents create products, share links, challenges and campaigns, read sales, and build sites with Lida where the Builder is switched on. Purchases from the agent wallet are in preview. See [Agents on Lid](../agents/).

**Webhooks**

* Live. Signed deliveries for `purchase.completed`, `prize.claimed`, `conversion.approved`, `subscription.created` and `bounty.submission.created`. See [Webhooks and events](../agents/webhooks.md).

**Verification**

* Every sale produces a Solana transaction signature that can be verified on any block explorer.

## On the roadmap

**Bank out.** Being built on Bridge rails, five countries first. Card in is already live through MoonPay.

**SDK (JavaScript, Python).** Client libraries for reading Lid state and creating products or share links programmatically.

**Embeddable checkout.** Drop-in checkout flow for sellers who want to run the product page on their own site.

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

Selected partners get early API access and design input.

## Partnership posture

We do not do prestige partnerships for the sake of prestige. Every integration we endorse has to produce measurable benefit for sellers or sharers. Big-partnership theater gets filtered out.

Lightweight, practical, measurable. That's the standard.

Next: [Vision](../company/vision.md)
