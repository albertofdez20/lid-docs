# Refunds and escrow

Refunds on Lid are a product setting, not a support queue. You choose the policy once, at creation, and the smart contract enforces it.

## The refund window

Every product carries a refund window, from 0 to 90 days:

* **0 days.** You are paid instantly and finally, in the sale transaction. No refunds. Right for cheap digital products where instant settlement is the whole point.
* **1 to 90 days.** The purchase sits in on-chain escrow for the window. If the buyer doesn't dispute, it releases to you automatically. If a dispute succeeds, the money returns to the buyer and the whole split reverses, including the affiliate's share.

## Why escrow instead of manual refunds

Manual refunds require trusting the seller to act. Escrow requires nothing: the program holds the funds and the rules execute either way. Buyers see the policy on the product page before paying, which is worth more than any "satisfaction guaranteed" badge.

## What it means for each side

* **Sellers** trade a settlement delay for buyer trust. Longer windows convert cautious buyers; 0 days maximizes cash flow.
* **Affiliates** earn when the sale sticks. With a window, commissions confirm when escrow releases.
* **Buyers** know the recourse before they pay, and it doesn't depend on anyone's goodwill.

Next: [FAQ for sellers →](faq.md)
