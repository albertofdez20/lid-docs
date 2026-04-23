# How it works

Every action on LID serves one loop.

**Create → Share → Sell → Get Paid**

## Create

A seller signs up and creates a digital product at [app.lid.pro](https://app.lid.pro). Title, description, price, file or access link. The whole flow is built to take minutes, not an afternoon.

The seller sets the affiliate commission at creation. Example: 20% of each sale to whoever drove it. That number is locked into the on-chain rules for that product.

No inventory tracking, no fulfillment pipelines, no shipping. The product page is the storefront. The smart contract is the cash register.

## Share

Every product on LID has a public link.

Anyone who wants to earn on the sale can generate an affiliate version of that link from the product page. The affiliate version carries an on-chain binding: when a buyer checks out through it, the attribution is recorded at the protocol level.

No application. No approval. No contract to countersign. The moment a seller turns on affiliate commission, every visitor is a potential distributor.

## Sell

A buyer lands on the product page. Checkout is designed to feel like software. No wallet jargon, no chain selection, no gas prompts. The buyer pays in USDC or fiat-to-USDC through an abstracted payment surface.

At the moment the transaction clears, two things happen atomically.

1. **The sale completes.** The buyer gets access to the product.
2. **The attribution binds.** If an affiliate link drove this sale, that affiliate is locked in as the beneficiary of the split.

Attribution is not a best-effort guess from a click database. It's a rule executed by the smart contract at checkout.

## Get Paid

In the same transaction as the sale, the split executes.

- **Seller** receives their share.
- **Affiliate** receives their commission, if one was attached.
- **LID** receives its 3% infrastructure fee.

All three payments settle in USDC in seconds. No reconciliation. No payout schedule. Money does not sit with LID between the sale and the payout. It is never touched.

The seller can off-ramp to fiat post-raise once the fiat partner is live. USDC is the native settlement asset.

## Why this matters

Every other model for creator commerce routes money through the platform. The platform holds the balance. The platform decides when you get paid. The platform decides how much to charge on the way out.

LID does none of that. The split is the transaction. The fee is transparent. The trust layer is the contract.

That's how "your customers are your sales team" becomes a real mechanism, not a slogan.

Next: [Quickstart →](quickstart.md)
