# Agentic Commerce API

In plain words: this page is about letting software, not just people, sell and buy on Lid. If you are a seller, nothing here changes how you use Lid.

**Status: the agent connection over MCP is live. The full public REST API and SDK are roadmap.**

Agents already run the loop today over MCP: create products, host files, share other people's products, open challenges and campaigns, review results, read sales and analytics, and receive signed webhooks. Purchases from the agent's own balance are in preview. Access is by API key, created in the app under **Settings > Developer** and used as a bearer token, with a REST mirror at `api.lid.pro/api/v1/agent/*`. Start at [Agents on Lid](../agents/) and the [Tool reference](../agents/tools.md).

What this page describes beyond that is direction, not a live reference. The final shape reflects design feedback from the developers and agent frameworks we work with before ship.

## Why it matters

If autonomous agents become meaningful economic actors over the next 12 to 24 months, they need native rails to transact with each other. Today, agents can call APIs, generate content, and reason. They cannot easily buy and sell products with on-chain attribution, split revenue automatically with other agents, or settle atomically in digital dollars.

Lid is a credible candidate for those rails because the core loop is already built for it. Permissionless distribution, enforceable attribution, atomic splits, instant settlement. All four are required properties for agent commerce to work at scale. Agents already create, share and read on the rail today.

## What the full API adds

Beyond what the MCP connection does today:

* Programmatic checkout for production money, with spending policies per key
* Attribution history per sharer and on-chain proofs per sale
* Weighted splits across several referrers
* Account-level analytics and exports
* An SDK (JavaScript, Python)

## Who it's for

**AI agent frameworks.** If you're building an agent that needs to discover products, attribute purchases, or split revenue with other agents, the API is the native rail.

**SaaS integrations.** If you're running a product and want to embed Lid's commerce loop (say, as a monetization primitive inside another creator tool), the API is how you plug in.

**Data consumers.** Marketplaces, aggregators, or analytics platforms that want to read Lid state for discovery, ranking, or reporting.

## What it's not today

* A public payments API for arbitrary USDC transfers. Lid routes commerce specifically. General-purpose payments are out of scope.
* A fiat on or off ramp. Bank out and card in are separate pieces, being built.

## Sequence

1. Harden the MCP connection with early design partners.
2. Engineer the full API surface.
3. Private beta with selected agent frameworks and integration partners.
4. Public API.

No date commitments. Things ship when they are ready.

## How to get involved early

If you're building an agent or integration that needs these primitives, we want to talk now. Early design partners shape the API surface.

Email [alberto@lid.pro](mailto:alberto@lid.pro) with a short description of what you're building and how you'd use the API. Selected partners get access to the private beta.

Next: [Integrations](integrations.md)
