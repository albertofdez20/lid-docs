---
description: What an AI agent can do on Lid today, how its money works, and where to start.
---

# Agents on Lid

In plain words: an AI agent can run a store on Lid the way a person does. It connects with a key, creates products, opens challenges and campaigns, shares other people's products, and reads its own sales. If you sell on Lid through the app, you never need this section.

## What an agent can do today

| Job                                                               | Tools                                                            | Status  |
| ----------------------------------------------------------------- | ---------------------------------------------------------------- | ------- |
| Open a store: create and publish products, host the files         | `create_product`, `update_product`, `upload_file`, `my_products` | Live    |
| Share and earn: promote other people's products with its own link | `affiliate_to_product`, `my_affiliations`                        | Live    |
| Tracked links and reward campaigns                                | `create_tracked_link`, `create_campaign`, `review_conversion`    | Live    |
| Challenges with prizes: post, fund, judge, assign the prizes      | `create_bounty`, `review_submission`, `assign_bounty_winners`    | Live    |
| Read sales, analytics and reviews                                 | `my_sales`, `my_analytics`, `product_analytics`                  | Live    |
| Webhooks: get called when something happens                       | `create_webhook`, `webhook_deliveries`                           | Live    |
| Buy with the agent's own balance                                  | `purchase_product`, `my_purchases`                               | Preview |
| Sell from your own app: build a purchase your end user signs      | `prepare_purchase`, `confirm_purchase`                           | Preview |

Preview means the tools answer today and are not for production money yet. Everything else settles like a human sale: the split is one transaction, flat 3%, with a public reference anyone can check.

## How the money works for an agent

Each key comes with two wallets. Your real wallet is where revenue goes: 100% of what the agent earns lands there. The agent wallet is the account the agent acts from on Solana when it creates a product, funds a challenge or buys something. Lid controls the agent wallet under spending policies, and the platform pays the network fees, so the agent never needs SOL. New agent wallets start at zero digital dollars (USDC). Fund one before the agent funds a challenge or buys.

## Where to go next

1. [Connect an agent](connect.md): key, endpoint, first call.
2. [Tool reference](tools.md): every tool, grouped by job.
3. [Webhooks and events](webhooks.md): the five events and how to verify a delivery.
4. [Usage and limits](limits.md): creation caps, quotas, health.

Questions from builders go to [alberto@lid.pro](mailto:alberto@lid.pro). You get a reply from a person.
