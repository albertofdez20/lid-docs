---
description: >-
  The REST API, the SDK and the Pay with Lid button: what each one does, where
  the key comes from, how to test, and where the full reference lives.
---

# API, SDK and buy button

In plain words: this page is for people who want their own software to work with Lid. If you build your site with Lida or sell through the app, nothing here changes how you use Lid.

## What can I build with?

Four pieces, all live.

| Piece               | What it is                                                                                                                                                                                   | Where                                                               |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| REST API            | The routes an agent has, over HTTPS: products, sales, challenges, links, campaigns and sites                                                                                                 | `https://api.lid.pro/api/v1`                                        |
| SDK                 | A typed client for the REST API, with retries, idempotency keys, one error class and webhook helpers. It runs in Node 20+ and edge runtimes, on your server, because it carries your API key | `@lidpro/sdk` on npm                                                |
| Pay with Lid button | One button on your site that sends the visitor to a Lid payment page. You handle no keys and no transactions                                                                                 | a script tag from `lid.pro/checkout.js`, or `@lidpro/pay` for React |
| MCP connection      | The same tools for an AI agent                                                                                                                                                               | `https://mcp.lid.pro/mcp`, see [Agents on Lid](../agents/)          |

The reference for every route, with its SDK call, curl and a sample response, is the developer guide at [lid.pro/en/docs](https://lid.pro/en/docs).

## Where does the key come from?

From **Settings → Development → Create API key**, with the permissions you choose. You send it as a bearer token, and the same key works over MCP and over REST. A call without the right permission answers `403 insufficient_scope`, and an expired key answers `401 key_expired`. See [Usage and limits](../agents/limits.md).

## How does the Pay with Lid button work?

The button opens a payment page hosted by Lid, at `lid.pro/en/checkout/` followed by the product's address. The buyer signs in on Lid and pays in digital dollars (USDC), and the seller is paid in that same transaction.

* You can pass `return_url`, `cancel_url` and `theme`.
* Pass a share code in `ref` and the sharer's commission is assigned in the same transaction.
* Lid sends the buyer back to your site with `lid_status`, `lid_product`, `lid_receipt` and `lid_signature`.
* Confirm the sale from your server with the `purchase.completed` webhook or with `GET /agent/sales`. A product with a refund window is held and sends no webhook: it shows in `GET /agent/sales` with kind `hold`.

## Can I test without real money?

Yes. The SDK takes `environment: 'devnet'`, which points at `https://api-devnet.lid.pro` and uses test USDC with no value.

## Can my own system talk to Lida?

Yes, over the REST API. `POST /lida/turns` chats with Lida and needs the **Chat with Lida** permission. `POST /lida/tasks` hands her a task and needs the **Lida tasks** permission. You send your instructions and your context with each request, and Lida treats your context as data. The developer guide covers the request format and how usage is counted.

## Can an AI agent create a digital product on Lid today?

Yes, over MCP or REST. An agent with a key creates a product, hosts the file, sets a commission for sharers, and reads its sales; when someone buys, the money settles in one transaction, flat 3%, into the key owner's real wallet. It can also build a site, share other people's products, run challenges and campaigns, review results, and receive signed webhooks. Start at [Agents on Lid](../agents/) and the [Tool reference](../agents/tools.md).

## What is it not?

* A public payments API for arbitrary USDC transfers. Lid settles sales. General-purpose payments are out of scope.
* A way to turn digital dollars into money in a bank. Adding funds by card is a separate piece, inside the app.

Questions go to [hello@lid.pro](mailto:hello@lid.pro), with a short description of what you are building.

Next: [Integrations](integrations.md)
