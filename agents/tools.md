# Tool reference

Every tool the Lid agent connection exposes, grouped by job. Names match the MCP catalog. Amounts: `priceUsdc` is in human units (`"5"` is five dollars); prize and reward amounts are atomic USDC strings (`"1000000"` is one dollar).

Each row says read, write or money. Write tools change state. Money tools move digital dollars (USDC) out of the agent wallet.

## Identity and health

| Tool              | Does                                                                                                  |
| ----------------- | ----------------------------------------------------------------------------------------------------- |
| `api_health`      | Is the API reachable. Read.                                                                           |
| `my_agent_wallet` | Who this key acts as: user id, real wallet (where revenue goes), agent wallet (acts on Solana). Read. |
| `get_my_usage`    | Creation caps with used and remaining, reset time, agent wallet balances. Read, free.                 |

## Products

| Tool                     | Does                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `create_product`         | Creates a product. Required: `name`, `priceUsdc`, `maxSupply`. Optional: description, cover, tags, commission (`affiliateCommissionBps`, 100 to 5000, default 1000), per-wallet limit, sale start time, translations. Revenue routes 100% to the key owner's real wallet. A paid product with no files is created as a draft. Courses are built in the dashboard. Write. |
| `update_product`         | Editorial fields: the files buyers download (`extraFiles`), cover, copy, publish or unpublish. Price, supply and commission are fixed at creation. Write.                                                                                                                                                                                                                |
| `upload_file`            | Hosts a file from a public URL, 25 MB max. `gated: true` returns a `key` for paid content; `gated: false` returns a public `url` for covers. Write.                                                                                                                                                                                                                      |
| `my_products`            | The products this key owns. Read.                                                                                                                                                                                                                                                                                                                                        |
| `product_analytics`      | Sales, volume, revenue, sharers and daily series for one product. Read.                                                                                                                                                                                                                                                                                                  |
| `get_reviews_by_product` | Reviews and average rating for a product. Read.                                                                                                                                                                                                                                                                                                                          |

## Share and earn

| Tool                            | Does                                                                                                   |
| ------------------------------- | ------------------------------------------------------------------------------------------------------ |
| `affiliate_to_product`          | Join a product as a sharer. Returns the share code and link. You cannot share your own product. Write. |
| `my_affiliations`               | Every product this key shares, with code, link, clicks, conversions and earnings. Read.                |
| `get_affiliate_by_code`         | Public lookup of a share code. Counts a click. Read.                                                   |
| `get_solana_affiliate_earnings` | Commission records and totals for a wallet. Read.                                                      |

## Links and campaigns

| Tool                     | Does                                                                                                                                                                                                                                            |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `create_tracked_link`    | A short link that counts clicks, referrers and results. Optional slug, optional campaign. Write.                                                                                                                                                |
| `list_my_links`          | Links this key owns or shares. Read.                                                                                                                                                                                                            |
| `get_link_analytics`     | Clicks, events, conversions and the funnel for one link. Read.                                                                                                                                                                                  |
| `create_campaign`        | A campaign with goals. Each goal names an event and a reward in atomic USDC. Attribution window 1 to 90 days, default 7. Rewarded conversions default to manual review. Goals with rewards need a funded pool before the campaign opens. Write. |
| `get_campaign_analytics` | The funnel across a campaign and its sharer ranking. Read.                                                                                                                                                                                      |
| `list_conversions`       | Conversions of your campaign by status: pending, approved, rejected, paid. Read.                                                                                                                                                                |
| `review_conversion`      | Approve or reject a pending conversion. Approved ones become payable. Write.                                                                                                                                                                    |

## Challenges

The API calls a challenge a bounty. Same thing.

| Tool                    | Does                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `create_bounty`         | Post a challenge: title, description, criteria, prizes by position, deadline. `fund: true` moves the prize from the agent wallet into the pool and opens it. You must pass `acceptTerms: true`: a challenge with money in the pool or entries received cannot be deleted, only archived; the pool only leaves toward the people you assign it to; the fee is charged at creation. Ask the human first. Write, money. |
| `list_bounties`         | Open challenges (public) or your own with `mine: true`. Read.                                                                                                                                                                                                                                                                                                                                                        |
| `get_bounty`            | One challenge with its pool state. Read.                                                                                                                                                                                                                                                                                                                                                                             |
| `list_submissions`      | Entries to your challenge, with evidence files. Read.                                                                                                                                                                                                                                                                                                                                                                |
| `review_submission`     | Mark an entry accepted, rejected or winner. Winner needs `assignedAmount`. Write.                                                                                                                                                                                                                                                                                                                                    |
| `assign_bounty_winners` | Assign every pending prize in the pool. Each prize holder then claims from their own wallet. Write, money.                                                                                                                                                                                                                                                                                                           |
| `get_bounty_winners`    | Prize holders and payment state: pending, assigned, claimed, with the public references. Read.                                                                                                                                                                                                                                                                                                                       |
| `get_pool`              | The pool by address: funded, assigned, paid out, with the full public ledger. Read.                                                                                                                                                                                                                                                                                                                                  |
| `my_pending_prizes`     | Prizes assigned to this key that are not claimed yet. Read.                                                                                                                                                                                                                                                                                                                                                          |

## Sales and analytics

| Tool                                     | Does                                                                                                                                    |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `my_sales`                               | What you sold, newest first, with the files as signed links so you can hand them to the buyer from your own app. Filter by buyer. Read. |
| `my_analytics`                           | Your numbers as a creator or as a sharer, over 7 days to all time. Read.                                                                |
| `search_creators`, `get_latest_creators` | Find creators by name, bio or country; who is new. Read.                                                                                |

## Webhooks

| Tool                              | Does                                                                                |
| --------------------------------- | ----------------------------------------------------------------------------------- |
| `create_webhook`                  | Register a URL for the events you pick. The signing secret is returned once. Write. |
| `list_webhooks`, `delete_webhook` | Your endpoints. Read, write.                                                        |
| `webhook_deliveries`              | Recent attempts for one endpoint, with status and error. Read.                      |

Details and the signature check: [Webhooks and events](webhooks.md).

## Preview: buying

These tools answer today. They are in preview: use them to test, not for production money.

| Tool                                            | Does                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `purchase_product`                              | Buy a product with the agent wallet's own balance. Pass `maxPriceUsdc` as a cap; if the price is higher nothing is signed. The agent wallet owns the receipt and downloads the content through `my_purchases`. Ask the human before spending. Write, money.                                          |
| `my_purchases`                                  | What the agent wallet bought, with the files as signed links. Read.                                                                                                                                                                                                                                  |
| `prepare_purchase`                              | Build an unsigned purchase for your own end user to sign inside your app, with an optional share code so the split pays the sharer. You then POST the signed transaction to `/api/v1/lidpro/sponsor` so the platform pays the network fee and broadcasts it. Nothing leaves the agent wallet. Write. |
| `confirm_purchase`                              | Confirm a purchase you broadcast, so the receipt and files show up in seconds. Safe to call twice. Write.                                                                                                                                                                                            |
| `prepare_usdc_transfer`, `prepare_sol_transfer` | Build an unsigned transfer for a wallet you control to sign. Nothing moves server side. Read.                                                                                                                                                                                                        |
