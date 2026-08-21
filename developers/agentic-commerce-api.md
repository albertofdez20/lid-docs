# Agentic Commerce API

In plain words: this page is about letting software, not just people, buy and sell on Lid. If you are a seller, nothing here changes how you use Lid.

**Status: the MCP write-surface v1 is live. The full public REST API is roadmap.**

Agents can already run the loop today over the Model Context Protocol: create a product, generate an affiliate link, initiate a checkout, and read settlement state. Access is by API key, created in the app under **Settings > Developer** (used as `Authorization: Bearer`), with signed webhooks (`x-lid-event`, `x-lid-timestamp`, `x-lid-signature`, HMAC-SHA256) for real-time events. It is early and scoped on purpose. Start at the [MCP quickstart](mcp-quickstart.md).

What this page describes beyond that (a full public REST API and SDK) is direction, not a live reference. The final shape will reflect design feedback from the developers and agent frameworks we're working with before ship.

## Why it matters

If autonomous agents become meaningful economic actors over the next 12 to 24 months, they need native rails to transact with each other. Today, agents can call APIs, generate content, and reason. They cannot easily buy and sell products with on-chain attribution, split revenue automatically with other agents, or settle atomically in digital dollars.

Lid is a credible candidate for those rails because the core loop is already built for it. Permissionless distribution, enforceable attribution, atomic splits, instant settlement. All four are required properties for agent commerce to work at scale. Agents already create and read on the rail today.

## What the API will support

**Product management**

* Create a product (title, description, price, commission rules)
* Update product metadata
* List products owned by a given account

**Affiliate links**

* Generate an affiliate link for a given product
* Query attribution history for a given affiliate

**Checkout and settlement**

* Programmatic checkout (agent-initiated purchase)
* Query transaction status
* Retrieve on-chain proofs for a given sale

**Webhooks**

* Real-time events for product created, sale completed, split settled, refund issued

**Analytics**

* Per-product performance
* Per-affiliate earnings
* Per-account transaction history

## Who it's for

**AI agent frameworks.** If you're building an agent that needs to discover products, attribute purchases, or split revenue with other agents, the API is the native rail.

**SaaS integrations.** If you're running a product and want to embed Lid's commerce loop (say, as a monetization primitive inside another creator tool), the API is how you plug in.

**Data consumers.** Marketplaces, aggregators, or analytics platforms that want to read Lid state for discovery, ranking, or reporting.

## What it's not today

* A public payments API for arbitrary USDC transfers. Lid routes commerce specifically. General-purpose payments are out of scope.
* A fiat on/off ramp. The fiat surface is a separate integration.
* A governance API. Governance lives elsewhere.

## Sequence

1. Harden the MCP write-surface v1 with early design partners.
2. Engineer the full API surface.
3. Private beta with selected agent frameworks and integration partners.
4. Public API launch.

No date commitments. Things ship when they are ready.

## How to get involved early

If you're building an agent or integration that needs these primitives, we want to talk now. Early design partners shape the API surface.

Email [alberto@lid.pro](mailto:alberto@lid.pro) with a short description of what you're building and how you'd use the API. Selected partners get access to the private beta.

Next: [Integrations →](integrations.md)
