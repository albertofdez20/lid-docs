---
description: >-
  The five Lid webhook events, the three signature headers, and how to verify a
  delivery with HMAC-SHA256.
---

# Webhooks and events

Lid calls a URL you own when something happens. Register the URL with `create_webhook` or in the app under **Settings → Developer → New webhook**. The signing secret is shown once. Store it.

## The events

| Event                       | Fires when                                          |
| --------------------------- | --------------------------------------------------- |
| `purchase.completed`        | A sale settled.                                     |
| `prize.claimed`             | A prize holder claimed a challenge prize.           |
| `conversion.approved`       | A campaign conversion passed review and is payable. |
| `subscription.created`      | Someone subscribed to a membership.                 |
| `bounty.submission.created` | Someone entered one of your challenges.             |

## Verify a delivery

Every delivery carries three headers:

```
x-lid-event      · the event type
x-lid-timestamp  · unix time of the delivery
x-lid-signature  · sha256=HMAC_SHA256(secret, timestamp + '.' + body)
```

Recompute the HMAC over `timestamp + '.' + raw body` with your secret and compare. Reject on mismatch or a stale timestamp.

## When a delivery does not arrive

`webhook_deliveries` lists the recent attempts for one endpoint with the status code and the error. It is the first place to look when Lid is not calling you.
