---
description: >-
  How Lid works under the hood: the Solana program, the three primitives, the
  developer surface (MCP, REST API, SDK, Pay with Lid button, webhooks) and the
  live stack.
---

# Overview

This section explains how Lid works under the hood. You do not need any of it to build a site or to sell on Lid; it exists for people who want to build on top of the same rails. If you are connecting an AI agent, start at [Agents on Lid](../agents/).

These pages stay high-level. The reference for every route is the developer guide at [lid.pro/en/docs](https://lid.pro/en/docs): the REST API, the SDK, the Pay with Lid button, webhooks, errors and Lida via API.

## What Lid is from a developer's perspective

Lid is the business suite, with one payment program on Solana underneath. At the primitive level, that program exposes three things.

1. **Product registration.** A product with a price and a commission rule for sharers (affiliates, in the API).
2. **Attribution binding.** A checkout routed through a share reference, enforced on-chain.
3. **Atomic splits.** A program that accepts payment and routes it to the seller, the sharer and Lid in the same transaction.

Today these primitives are reached four ways: the Lid web app, the agent connection over MCP, the REST API with its SDK, and the Pay with Lid button. See [API, SDK and buy button](agentic-commerce-api.md).

## Who this section is for

* **Developers** who want to understand the Lid architecture before integrating.
* **Agent builders** thinking about how autonomous software actors will transact.
* **Integration partners** who want to embed Lid functionality in their own product.
* **Security researchers** who want to responsibly disclose issues.

If you want a site or you sell on Lid, none of this is required reading. Everything you need is in [Start here](../getting-started/what-is-lid.md).

## Architecture at a glance

* **Chain:** Solana mainnet
* **Settlement asset:** USDC (native SPL token)
* **Attribution enforcement:** Solana program
* **Product metadata:** on-chain plus a metadata storage layer
* **Checkout UX:** hosted by Lid, abstracted (no wallet exposure for end users)
* **Wallet and auth:** Privy embedded wallet, live in production
* **Card in:** live, inside the app, through MoonPay
* **Developer surface:** the MCP connection at `mcp.lid.pro`, a REST API at `api.lid.pro/api/v1`, the SDK (`@lidpro/sdk`), the Pay with Lid button (`@lidpro/pay`), API keys with permissions and signed webhooks under Settings > Development

## Why Solana

Three properties were required. Only Solana delivered all three at the scale Lid needs.

1. **Stablecoin depth.** USDC on Solana has the liquidity to settle real-world commerce.
2. **Sub-second confirmation.** A payment confirms in under a second, so checkout feels like software, not like waiting for block confirmations.
3. **Low cost.** Network fees are sub-cent, so they don't eat into splits.

## Design principles

**Atomic splits or nothing.** Every transaction either settles all parties or none. No half-states.

**Attribution at checkout, not at click.** A click is a signal. A checkout is a commitment. Attribution binds at the moment of commitment.

**Abstracted UX.** The blockchain is invisible. Developers integrating Lid should be able to keep that abstraction for their end users.

**Permissionless distribution.** The program does not gate who can participate in selling. Rules at the product level, not at the user level.

**The 3% fee is a protocol primitive.** It's part of the split logic, not a billing layer on top.

## Live stack

* **Privy** · embedded wallet and auth. Live.
* **MoonPay** · adding funds by card. Live.
* **Alchemy** · Solana RPC. Live.
* **Pinata** · IPFS metadata storage. Live.
* **Solana Pay** · checkout UX. Live.
* **USDC SPL Token** · settlement asset. Live.

## What's live today

* Solana mainnet deployment
* The program that enforces splits and fees
* Product creation and checkout through the web app
* USDC settlement
* Privy embedded wallet and authentication
* Sites built with Lida, open to every account
* Courses, memberships, challenges and tracked links
* Adding funds by card
* The agent connection over MCP: agents build sites, create products, share links, run challenges, read sales and work a site's admin. Signed webhooks.
* The REST API at `api.lid.pro/api/v1`, the SDK `@lidpro/sdk` on npm, and the Pay with Lid button

## How to get involved

* **Build on Lid:** start with the developer guide at [lid.pro/en/docs](https://lid.pro/en/docs). Questions go to [hello@lid.pro](mailto:hello@lid.pro).
* **Security research:** responsible disclosure to [hello@lid.pro](mailto:hello@lid.pro). Handled privately and prioritized.
* **Agent frameworks:** if you're building an autonomous agent that needs economic rails, write to us with what you are making.

Next: [The Solana program](solana-program.md)
