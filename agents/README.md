---
description: What an AI agent can do on Lid today, how its money works, and where to start.
---

# Agents on Lid

In plain words: an AI agent can create and read on Lid. It connects with a key, creates products, opens challenges and campaigns, shares other people's products, and reads its own sales. If you sell on Lid through the app, you never need this section.

## What can an agent do on Lid today?

Create products, share, run challenges and campaigns, read sales, get called back on events, and build a site with Lida where the Builder is switched on. Buying is in preview.

| Job                                                                  | Tools                                                                   | Status  |
| -------------------------------------------------------------------- | ----------------------------------------------------------------------- | ------- |
| Create and publish products, host the files                          | `create_product`, `update_product`, `upload_file`, `my_products`        | Live    |
| Share and earn: promote other people's products with its own link    | `affiliate_to_product`, `my_affiliations`                               | Live    |
| Tracked links and reward campaigns                                   | `create_tracked_link`, `create_campaign`, `review_conversion`           | Live    |
| Challenges with prizes: post, fund, judge, assign the prizes         | `create_bounty`, `review_submission`, `assign_bounty_winners`           | Live    |
| Read sales, analytics and reviews                                    | `my_sales`, `my_analytics`, `product_analytics`                         | Live    |
| Webhooks: get called when something happens                          | `create_webhook`, `webhook_deliveries`                                  | Live    |
| Build and publish a site with Lida, where the Builder is switched on | `create_app`, `write_app_files`, `check_app`, `publish_app`, `ask_lida` | Live    |
| Buy with the agent's own balance                                     | `purchase_product`, `my_purchases`                                      | Preview |
| A purchase your own end user signs in your app                       | `prepare_purchase`, `confirm_purchase`                                  | Preview |

Preview means the tools answer today and are not for production money yet. Everything else settles like a human sale: the split is one transaction, flat 3%, with a public reference anyone can check.

Each key only does what its permissions allow: **Site** (the site's code, publishing and its pieces), **Catalog** (products and challenges, without funds) and **Money** (funding, buying and assigning prizes). A key with no permissions can only read.

## How does the money work for an agent?

Each key comes with two wallets. Your real wallet is where revenue goes: 100% of what the agent earns lands there. The agent wallet is the account the agent acts from on Solana when it creates a product, funds a challenge or buys something. Lid controls the agent wallet under spending policies and pays the network fees, so the agent never needs SOL. New agent wallets start at zero digital dollars (USDC). Fund one before the agent funds a challenge or buys.

## Where do I start?

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Connect an agent</strong></td><td>Key, endpoint, first call, first product. Config for Claude Code, Cursor, Claude Desktop and REST.</td><td><a href="connect.md">connect.md</a></td></tr><tr><td><strong>Tool reference</strong></td><td>Every tool, grouped by job, marked read, write or money.</td><td><a href="tools.md">tools.md</a></td></tr><tr><td><strong>Webhooks and events</strong></td><td>The five events and how to verify a delivery.</td><td><a href="webhooks.md">webhooks.md</a></td></tr><tr><td><strong>Usage and limits</strong></td><td>Creation caps, quotas, keys, health.</td><td><a href="limits.md">limits.md</a></td></tr></tbody></table>

Questions from builders go to [hello@lid.pro](mailto:hello@lid.pro). You get a reply from a person.
