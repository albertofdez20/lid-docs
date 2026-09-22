# Overview

This section explains how Lid works under the hood. You do not need any of it to sell or share on Lid; it exists for people who want to build on top of the same rails. If you are connecting an AI agent, start at [Agents on Lid](../agents/) instead: that is the live developer surface today.

It is intentionally high-level. Full technical reference, program interfaces and endpoint specs publish when the API surface stabilizes.

## What Lid is from a developer's perspective

Lid is the creator suite, with one payment program on Solana underneath. At the primitive level, that program exposes three things.

1. **Product registration.** A product with a price and a commission rule for sharers (affiliates, in the API).
2. **Attribution binding.** A checkout routed through a share reference, enforced on-chain.
3. **Atomic splits.** A program that accepts payment and routes it to the seller, the sharer and Lid in the same transaction.

Today these primitives are consumed through the Lid web app and the agent connection over MCP, where agents run the same loop a person does. The roadmap exposes them as a full public API.

## Who this section is for

* **Developers** who want to understand the Lid architecture before integrating.
* **Agent builders** thinking about how autonomous software actors will transact.
* **Integration partners** who want to embed Lid functionality in their own product.
* **Security researchers** who want to responsibly disclose issues.

If you're a seller or a sharer, none of this is required reading. Everything you need is in [Start here](../getting-started/what-is-lid.md).

## Architecture at a glance

* **Chain:** Solana mainnet
* **Settlement asset:** USDC (native SPL token)
* **Attribution enforcement:** Solana program
* **Product metadata:** on-chain plus a metadata storage layer
* **Checkout UX:** hosted by Lid, abstracted (no wallet exposure for end users)
* **Wallet and auth:** Privy embedded wallet, live in production
* **Card in:** partner on-ramp, being built
* **Bank out:** Bridge rails, five countries first, being built
* **Developer surface today:** the web app, the MCP connection at `mcp.lid.pro`, a REST mirror at `api.lid.pro/api/v1/agent/*`, API keys and signed webhooks under Settings > Developer
* **Developer surface, roadmap:** Agentic Commerce API plus SDK

## Why Solana

Three properties were required. Only Solana delivered all three at the scale Lid needs.

1. **Stablecoin depth.** USDC on Solana has the liquidity to settle real-world commerce.
2. **Sub-second finality.** Checkout has to feel like software, not like waiting for block confirmations.
3. **Low cost.** Network fees are sub-cent. Splits don't get eaten by gas.

## Design principles

**Atomic splits or nothing.** Every transaction either settles all parties or none. No half-states.

**Attribution at checkout, not at click.** A click is a signal. A checkout is a commitment. Attribution binds at the moment of commitment.

**Abstracted UX.** The blockchain is invisible. Developers integrating Lid should be able to keep that abstraction for their end users.

**Permissionless distribution.** The program does not gate who can participate in selling. Rules at the product level, not at the user level.

**The 3% fee is a protocol primitive.** It's part of the split logic, not a billing layer on top.

## Live stack

* **Privy** · embedded wallet and auth. Live.
* **Alchemy** · Solana RPC. Live.
* **Pinata** · IPFS metadata storage. Live.
* **Solana Pay** · checkout UX. Live.
* **USDC SPL Token** · settlement asset. Live.
* **Card in** · partner on-ramp. Being built.
* **Bridge** · bank out. Being built. Owned by Darwin.
* **Helius webhooks** · transaction monitoring. Planned.
* **x402 / ACP** · long-term horizon.

## What's live today

* Solana mainnet deployment
* The program that enforces splits and fees
* Product creation and checkout through the web app
* USDC settlement
* Privy embedded wallet and authentication
* Courses, services with protected payment, memberships, challenges, campaigns, tracked links
* The agent connection over MCP: agents create products, share links, challenges and campaigns, and read sales. Signed webhooks. Purchases from the agent wallet are in preview.

## What's on the roadmap

* **Agentic Commerce API.** REST and SDK surface for developers and AI agents to create products, generate share links, and route transactions programmatically, with production purchases under spending policies.
* **Multi-sharer attribution.** Weighted splits for sales driven by multiple referrers.
* **White-label embedding.** Embeddable checkout on partner sites.

Details in [Agentic Commerce API](agentic-commerce-api.md).

## How to get involved

* **Build on Lid:** email [alberto@lid.pro](mailto:alberto@lid.pro) for the integration waitlist.
* **Security research:** responsible disclosure to [alberto@lid.pro](mailto:alberto@lid.pro). Handled privately and prioritized.
* **Agent frameworks:** if you're building an autonomous agent that needs economic rails, we want to talk now, before the full API ships, so the design reflects what agents actually need.

Next: [Smart contracts](smart-contracts.md)
