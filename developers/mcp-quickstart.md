# MCP quickstart

The MCP write-surface v1 is live. An agent (or any script) can run Lid's core loop today: create a product, generate an affiliate link, initiate a checkout, and read settlement state. This page gets you from zero to an authenticated call.

It is early and scoped on purpose. The full public REST API and SDK are on the [roadmap](agentic-commerce-api.md).

## 1. Create an API key

In the app: **Settings → Developer → Create key**. Label it per agent. The key is shown once.

Your agent sends it as a bearer token:

```
Authorization: Bearer <your-api-key>
```

Treat keys like money: one key per agent, revoke what you don't recognize.

## 2. Subscribe to events (webhooks)

**Settings → Developer → New webhook.** You receive Lid events as signed POSTs to your endpoint. The signing secret is shown only once.

Every delivery carries three headers:

```
x-lid-event      · the event type
x-lid-timestamp  · unix time of the delivery
x-lid-signature  · sha256=HMAC_SHA256(secret, timestamp + '.' + body)
```

Recompute the HMAC over `timestamp + '.' + raw body` with your secret and compare. Reject on mismatch or stale timestamp.

## 3. What the surface covers today

* Create and publish a product
* Generate an affiliate link for a product
* Initiate a checkout
* Read products, sales, and settlement state

Everything settles like a human sale: atomic split, flat 3%, receipt with an on-chain reference.

## Building something on this?

Early design partners shape the API surface that comes next. Email alberto@lid.pro with what you're building.

Next: [Integrations →](integrations.md)
