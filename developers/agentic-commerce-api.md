---
description: >-
  The agent connection over MCP is live; the full REST API and SDK are roadmap.
  What it adds, who it is for, how to get in early.
---

# Agentic Commerce API

In plain words: this page is about letting software, not just people, sell and buy on Lid. If you are a seller, nothing here changes how you use Lid.

## Can an AI agent sell a digital product today?

Yes, on Lid, over MCP, today. An agent with a key creates a product, hosts the file, sets a commission for sharers, and reads its sales; the money settles in one transaction, flat 3%, into the key owner's real wallet. It can also share other people's products, run challenges and campaigns, review results, and receive signed webhooks. Purchases from the agent's own balance are in preview. Access is by API key from **Settings > Developer**, used as a bearer token, with a REST mirror at `api.lid.pro/api/v1/agent/*`. Start at [Agents on Lid](../agents/) and the [Tool reference](../agents/tools.md).

**Status: the agent connection over MCP is live. The full public REST API and SDK are roadmap.** What this page describes beyond the live surface is direction, not a reference.

## Why does agent commerce need its own rails?

If autonomous agents become meaningful economic actors over the next 12 to 24 months, they need native rails to transact with each other. Today, agents can call APIs, generate content, and reason. They cannot easily buy and sell products with on-chain attribution, split revenue automatically with other agents, or settle atomically in digital dollars.

Lid is a credible candidate for those rails because the core loop is already built for it. Permissionless distribution, enforceable attribution, atomic splits, instant settlement. All four are required properties for agent commerce to work at scale. Agents already create, share and read on the rail today.

## What will the full API add?

Beyond what the MCP connection does today:

* Programmatic checkout for production money, with spending policies per key
* Attribution history per sharer and on-chain proofs per sale
* Weighted splits across several referrers
* Account-level analytics and exports
* An SDK (JavaScript, Python)

## Who is it for?

**AI agent frameworks.** If you're building an agent that needs to discover products, attribute purchases, or split revenue with other agents, the API is the native rail.

**SaaS integrations.** If you're running a product and want to embed Lid's commerce loop (say, as a monetization primitive inside another creator tool), the API is how you plug in.

**Data consumers.** Marketplaces, aggregators, or analytics platforms that want to read Lid state for discovery, ranking, or reporting.

## What is it not?

* A public payments API for arbitrary USDC transfers. Lid routes commerce specifically. General-purpose payments are out of scope.
* A fiat on or off ramp. Bank out and card in are separate pieces, being built.

## In what order does it ship?

1. Harden the MCP connection with early design partners.
2. Engineer the full API surface.
3. Private beta with selected agent frameworks and integration partners.
4. Public API.

No date commitments. Things ship when they are ready.

## How do I get in early?

If you're building an agent or integration that needs these primitives, we want to talk now. Early design partners shape the API surface. Email [alberto@lid.pro](mailto:alberto@lid.pro) with a short description of what you're building and how you'd use the API. Selected partners get access to the private beta.

Next: [Integrations](integrations.md)
