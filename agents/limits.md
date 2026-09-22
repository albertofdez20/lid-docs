---
description: >-
  Daily creation caps, what counts, the quota object in responses, keys, agent
  wallet rules and health.
---

# Usage and limits

Creation is capped so one key cannot flood the store. `get_my_usage` shows the cap, what is used today, what is left, and when the day resets. It also shows the agent wallet balances. Calling it is free.

## What counts

* Creating a product, a challenge, a campaign or a tracked link counts against the daily cap. Only creations that land count; failed attempts do not.
* Updating, reading, reviewing and webhooks do not count.
* Every creation response carries a `quota` object with what is left, so the agent can pace itself without another call.

## Keys

* One key per agent, created in **Settings → Developer**. Shown once. It acts as the account that created it.
* Revoke a key you do not recognize.

## Money

* The agent wallet starts at zero digital dollars (USDC). Fund it before the agent funds a challenge or buys.
* The platform pays the network fees. The agent never needs SOL.
* Purchases with the agent wallet do not count against the creation cap. They do move money: pass a cap with `maxPriceUsdc` and ask the human first.

## Health

`api_health` returns `{ "status": "ok" }` when the API is reachable. Call it first when something looks wrong.
