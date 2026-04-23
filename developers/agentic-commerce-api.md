# Agentic Commerce API

**Status: Roadmap. Launches post-raise.**

The Agentic Commerce API is LID's programmable surface for developers and autonomous agents. It exposes the same primitives the web app uses today (product creation, affiliate binding, atomic settlement) as first-class API calls and SDK methods.

This page describes the direction. It is not a live reference. The final shape will reflect design feedback from the developers and agent frameworks we're working with before ship.

## Why it matters

If autonomous agents become meaningful economic actors over the next 12 to 24 months, they need native rails to transact with each other. Today, agents can call APIs, generate content, and reason. They cannot easily buy and sell products with on-chain attribution, split revenue automatically with other agents, or settle atomically in stablecoins.

LID is a credible candidate for that infrastructure because the core loop is already built for it. Permissionless distribution, enforceable attribution, atomic splits, instant settlement. All four are already required properties for agent commerce to work at scale.

## What the API will support

**Product management**

- Create a product (title, description, price, commission rules)
- Update product metadata
- List products owned by a given account

**Affiliate links**

- Generate an affiliate link for a given product
- Query attribution history for a given affiliate

**Checkout and settlement**

- Programmatic checkout (agent-initiated purchase)
- Query transaction status
- Retrieve on-chain proofs for a given sale

**Webhooks**

- Real-time events for product created, sale completed, split settled, refund issued

**Analytics**

- Per-product performance
- Per-affiliate earnings
- Per-account transaction history

## Who it's for

**AI agent frameworks.** If you're building an agent that needs to discover products, attribute purchases, or split revenue with other agents, the API is the native rail.

**SaaS integrations.** If you're running a product and want to embed LID's commerce loop (say, as a monetization primitive inside another creator tool), the API is how you plug in.

**Data consumers.** Marketplaces, aggregators, or analytics platforms that want to read LID state for discovery, ranking, or reporting.

## What it's not (yet)

- A public payments API for arbitrary USDC transfers. LID routes commerce specifically. General-purpose payments are out of scope.
- A fiat on/off ramp. The fiat surface is a separate integration on the roadmap.
- A governance API. Governance lives elsewhere.

## Timeline

The API is part of the post-raise engineering scope.

Sequence:

1. Close the $500K pre-seed raise.
2. Engineer the API surface.
3. Private beta with selected agent frameworks and integration partners.
4. Public API launch.

No date commitments before the raise closes.

## How to get involved early

If you're building an agent or integration that needs these primitives, we want to talk now. Early design partners shape the API surface.

Email alberto@lid.pro with a short description of what you're building and how you'd use the API. Selected partners get access to the private beta.

Next: [Integrations →](integrations.md)
