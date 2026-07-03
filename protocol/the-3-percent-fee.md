# The 3% fee

Lid charges 3% of every transaction. That's the whole pricing model today, and the 3% is a permanent floor. No subscriptions. No listing fees. No withdrawal fees. No holdbacks.

## Why 3%

The fee is a strategic choice, not a default.

Most creator commerce platforms land between 5% and 30% effective take rate once payment processing, monthly subscriptions, listing fees, and payout costs are added up. Gumroad's effective take rate is around 13%. Stripe adds 2.9% + $0.30 on top of most storefronts. Whop runs 3 to 10% depending on product type. Stan Store layers variable fees on top of a monthly subscription.

3% is deliberate for three reasons.

**Low enough to align with top earners.** The more a seller grows, the less they feel Lid. A seller doing $50K/month isn't punished for scale. On a 10% platform, that seller pays $5K/month in fees. On Lid, $1,500.

**Strong enough to keep Lid sustainable.** Combined with an optional Pro tier for advanced tools, in build, the unit economics support venture-scale growth. See [the illustrative unit-economics assumptions in the vision doc](../company/vision.md).

**Durable enough to block incumbents.** A 3% fee is a pricing moat. Any incumbent that matches it has to gut their existing revenue model. They can't match without breaking their P\&L. So they won't.

## What the 3% covers

The 3% covers the rails. The smart contract that splits payment between seller, affiliate, and Lid. The atomic settlement. The on-chain attribution that holds up under audit. Lid never holds your money. No escrow. No subscription required (today). No currency conversion charge today, because everything settles in digital dollars. When fiat rails ship (planned), conversion will pass through at cost.

Specifically, the 3% pays for:

* Infrastructure to route splits atomically.
* The smart contract that enforces attribution.
* Product page hosting and delivery.
* Buyer checkout flow.
* Seller dashboard.
* Affiliate dashboard.
* Support during alpha (every case goes through the founder).

The Bridge fiat on/off-ramp is integrating at the edges. The 3% covers the rails inside Lid.

## When the model evolves

The optional Pro tier is in build. The lead Pro feature is creator-to-buyer communication: email and community tools that close the gap between you and the people who buy from you. Analytics, custom branding, advanced attribution, and priority support sit alongside it. Pro lands at around $29 per month with the 3% transaction fee unchanged.

The core loop (create, share, sell, get paid) stays on the flat 3% without a subscription. Pro sells tools on top. It never gates the four steps.

No timeline has been committed for the Pro launch. It ships when the features are real enough to justify charging for them.

## The broader point

The fee structure is part of the trust architecture. A platform that charges 20% and holds your money for 30 days is extracting rent. A platform that charges 3% and settles in seconds is infrastructure.

We built Lid to be the second one.

Next: [Security and guarantees →](security-and-guarantees.md)
