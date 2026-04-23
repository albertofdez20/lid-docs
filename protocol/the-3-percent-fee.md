# The 3% fee

LID charges 3% of every transaction. That's the whole pricing model today. No subscriptions. No listing fees. No withdrawal fees. No holdbacks.

## Why 3%

The fee is a strategic choice, not a default.

Most creator commerce platforms land between 5% and 30% effective take rate once payment processing, monthly subscriptions, listing fees, and payout costs are added up. Gumroad's effective take rate is around 13%. Stripe adds 2.9% + $0.30 on top of most storefronts. Whop runs 3 to 10% depending on product type. Stan Store layers variable fees on top of a monthly subscription.

3% is deliberate for three reasons.

**Low enough to align with top earners.** The more a seller grows, the less they feel LID. A seller doing $50K/month isn't punished for scale. On a 10% platform, that seller pays $5K/month in fees. On LID, $1,500.

**Strong enough to keep LID sustainable.** Combined with a planned Pro tier for advanced features, the unit economics support venture-scale growth. See [blended ARPU math in the vision doc](../company/vision.md).

**Durable enough to block incumbents.** A 3% fee is a pricing moat. Any incumbent that matches it has to gut their existing revenue model. They can't match it without breaking their P&L, so they won't.

## What the 3% covers

- Infrastructure to route splits atomically.
- The smart contract that enforces attribution.
- Product page hosting and delivery.
- Buyer checkout flow.
- Seller dashboard.
- Affiliate dashboard.
- Support during alpha (every case goes through the founder).

## What the 3% is not

- It's not an escrow fee. LID never holds your money.
- It's not a payment processing fee. Solana network fees are separate (sub-cent).
- It's not a currency conversion fee. Settlement is in USDC 1:1.
- It's not a subscription. You pay only when you transact.

## When the model evolves

A Pro tier is planned for when the product earns the right to charge for it. The expected structure:

| Tier | Transaction fee | Monthly | Who it's for |
|---|---|---|---|
| **Free** | 5% | $0 | Casual sellers, single-product launches. |
| **Pro** | 3% | ~$29 | Active sellers who want analytics and custom branding. |
| **Enterprise** | Custom | Custom | High-volume partners, API integrations, white-label. |

When Pro launches, the current 3% rate will be preserved for existing sellers during the transition. The core loop (create, share, sell, get paid) will always be available on the Free tier. Subscriptions add advanced tools. They do not gate core functionality.

No timeline has been committed for the Pro launch. It happens when the features are real enough to justify charging for them.

## The broader point

The fee structure is part of the trust architecture. A platform that charges 20% and holds your money for 30 days is extracting rent. A platform that charges 3% and settles in seconds is infrastructure.

We built LID to be the second one.

Next: [Security and guarantees →](security-and-guarantees.md)
