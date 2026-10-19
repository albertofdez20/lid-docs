---
description: >-
  Creation caps per key, by day and over the key's life, what counts, the quota
  object in responses, the rate limit, key permissions and expiry, agent wallet
  rules and health.
---

# Usage and limits

Creation is capped per key, by day and over the key's life, so one key cannot flood the store. `get_my_usage` shows the caps, what is used today, what is left, and when the day resets. It also shows the agent wallet balances. Calling it is free.

## What counts

* Creating a product, a challenge, a campaign or a tracked link counts against the caps. Only creations that land count; failed attempts do not.
* Updating, reading, reviewing and webhooks do not count.
* Every creation response carries a `quota` object with what is left today and over the key's life, so the agent can pace itself without another call.

## Rate limit

About 60 requests per minute per key, across all tools. Past that, or past a creation cap, calls answer `429`; wait and try again.

## Keys

* One key per agent, created in **Settings → Developer**. Shown once. It acts as the account that created it.
* A key only does what its permissions allow: **Site**, **Catalog** and **Money**. With none, it can only read. A call without the right permission answers `403 insufficient_scope`.
* A key expires after 30, 90 or 180 days, as chosen when it was created. An expired key answers `401 key_expired`.
* Revoke a key you do not recognize.

## Money

* The agent wallet starts at zero digital dollars (USDC). Fund it before the agent funds a challenge or buys.
* Lid pays the network fees. The agent never needs SOL.
* Purchases with the agent wallet do not count against the creation cap. They do move money: pass a cap with `maxPriceUsdc` and ask the human first.
* Over REST, send an `Idempotency-Key` header on calls that move money, so a retried call with the same key is not processed twice.

## Health

`api_health` returns `{ "status": "ok" }` when the API is reachable. Call it first when something looks wrong.
