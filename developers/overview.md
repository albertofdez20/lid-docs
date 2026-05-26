# Overview

This section is intentionally high-level during the alpha phase. Full technical reference, contract ABIs, and endpoint specs publish when the API surface stabilizes post-raise.

## What LID is from a developer's perspective

LID is programmable commerce infrastructure on Solana.

At the primitive level, LID exposes three things.

1. **Product creation.** A way to register a digital product with a price and an affiliate commission rule.
2. **Attribution binding.** A way to route a checkout through an affiliate reference, enforced on-chain.
3. **Atomic splits.** A smart contract that accepts payment and routes to the seller, affiliate, and LID in the same transaction.

Today these primitives are consumed through the LID web app. The roadmap exposes them as API and on-chain rails for developers and AI agents to integrate directly.

## Who this section is for

* **Developers** who want to understand the LID architecture before integrating.
* **Agent builders** thinking about how autonomous software actors will transact.
* **Integration partners** who want to embed LID functionality in their own product.
* **Security researchers** who want to responsibly disclose or audit the system.

If you're a seller or affiliate, none of this is required reading. Everything you need is in the [Getting started](/getting-started/what-is-lid.md) section.

## Architecture at a glance

* **Chain:** Solana mainnet
* **Settlement asset:** USDC (native SPL token)
* **Attribution enforcement:** Solana program (smart contract)
* **Product metadata:** On-chain plus metadata storage layer
* **Checkout UX:** Hosted by LID, abstracted (no wallet exposure for end users)
* **Wallet and auth:** Privy embedded wallet (live in production)
* **Fiat on-ramp and off-ramp:** Bridge (live in production)
* **Developer surface (today):** Web app
* **Developer surface (roadmap):** Agentic Commerce API plus SDK

## Why Solana

Three properties were required. Only Solana delivered all three at the scale LID needs.

1. **Stablecoin depth.** USDC on Solana has the liquidity to settle real-world commerce.
2. **Sub-second finality.** Checkout has to feel like software, not like waiting for block confirmations.
3. **Low cost.** Network fees are sub-cent. Splits don't get eaten by gas.

## Design principles

**Atomic splits or nothing.** Every transaction either settles all parties or none. No half-states.

**Attribution at checkout, not at click.** A click is a signal. A checkout is a commitment. Attribution binds at the moment of commitment.

**Abstracted UX.** The blockchain is invisible infrastructure. Developers integrating LID should be able to keep that abstraction for their end users.

**Permissionless distribution.** The protocol does not gate who can participate in selling. Rules at the product level, not at the user level.

**The 3% fee is a protocol primitive.** It's part of the split logic, not a billing layer on top.

## Live stack

* **Privy** · embedded wallet and auth. Live.
* **Alchemy** · Solana RPC. Live.
* **Pinata** · IPFS metadata storage. Live.
* **Solana Pay** · checkout UX. Live.
* **USDC SPL Token** · settlement asset. Live.
* **Bridge** · fiat rails. Live. Owned by Darwin.
* **Helius webhooks** · transaction monitoring. Planned.
* **x402 / ACP** · Year 2 horizon.

## What's live today

* Solana mainnet deployment
* Smart contract that enforces splits and fees
* Product creation and checkout through the web app
* USDC settlement
* Privy embedded wallet and authentication
* Fiat on-ramp and off-ramp. Bridge. Live in production.

## What's on the roadmap (post-raise)

* **Agentic Commerce API.** REST and SDK surface for developers and AI agents to create products, generate affiliate links, and route transactions programmatically.
* **Webhooks.** Real-time event delivery (product created, sale completed, split settled) for integration with external systems.
* **Multi-affiliate attribution.** Weighted splits for sales driven by multiple referrers.
* **White-label embedding.** Enterprise tier with embeddable checkout on partner sites.

Details in [Agentic Commerce API →](/developers/agentic-commerce-api.md)

## How to get involved

* **Build on LID:** email <alberto@lid.pro> for the integration waitlist.
* **Security research:** responsible disclosure to <alberto@lid.pro>. Handled privately and prioritized.
* **Agent frameworks:** if you're building an autonomous agent that needs economic rails, we want to talk now, before the API ships, so the design reflects what agents actually need.

Next: [Smart contracts →](/developers/smart-contracts.md)
