---
description: >-
  Creation caps per key, by day and over the key's life, what counts, the quota
  object in responses, the rate limit, key permissions and expiry, site limits,
  agent wallet rules and health.
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

* One key per agent, created in **Settings → Development**. It acts as the account that created it, and you can show it again there with **Show key**.
* A key only does what its permissions allow: **Site**, **Catalog**, **Money**, **People data and sales**, **Lida tasks** and **Chat with Lida**. With none, it can only read. A call without the right permission answers `403 insufficient_scope`.
* A key that only works for Lida tasks answers `403 key_tasks_only` on other calls.
* A key expires after 30, 90 or 180 days, as chosen when it was created. An expired key answers `401 key_expired`.
* Remove a key you do not recognize.

## Sites

* `create_app`: 3 a minute and 10 a day, inside the account's site limit.
* `write_app_files`: a site holds up to 80 files, 64 KB per file and 600 KB in total, and one call carries up to 2 MB.
* `screenshot_app`: 3 a minute, one at a time.
* `upload_app_image`: up to 8 MB per image.
* `upload_file`: up to 25 MB per file.

## Money

* The agent wallet starts at zero digital dollars (USDC). Fund it before the agent funds a challenge.
* Lid pays the network fees. The agent never needs SOL.
* Over REST, send an `Idempotency-Key` header on calls that move money, so a retried call with the same key is not processed twice.

## Health

`api_health` returns `{ "status": "ok" }` when the API is reachable. Call it first when something looks wrong.
