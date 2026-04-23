# Instant splits

Every sale on LID splits money in the same transaction it collects it.

## The mechanic

A transaction on LID contains a series of instructions that execute atomically. For a simple sale with one affiliate, those instructions look like this:

1. Buyer pays the full price in USDC.
2. Seller's share routes to the seller's account.
3. Affiliate's share routes to the affiliate's account.
4. LID's 3% routes to LID.
5. Access to the product is granted to the buyer.

If any instruction fails, the whole transaction reverts. Either all parties move together or no one moves.

This is atomicity. It's the property that makes a split trustable without arbitration.

## Why this changes the game

On a traditional platform, "instant split" is marketing. What actually happens:

- The platform collects the full payment.
- The commission is recorded in the platform's database.
- The payout is queued to a scheduler.
- Days or weeks later, money is released.

During that window, the money lives with the platform. The platform earns yield on it, decides when to release it, and holds leverage over both the seller and the affiliate.

On LID, there is no window. The split is the transaction. The platform never holds anyone's money.

## Split types LID supports today

**Two-way split.** Seller and LID. No affiliate involved. Seller gets 97%, LID gets 3%.

**Three-way split.** Seller, affiliate, and LID. The affiliate percentage is set by the seller at product creation. LID still gets 3% of the total.

**Fixed-rule splits.** All splits on LID today are percentage-based and fixed at the moment of product creation.

## Split types on the roadmap

Once the core loop is proven at scale, the split types expand:

- **Multi-affiliate attribution.** Multiple affiliates who contributed to a sale, with weighted splits.
- **Team splits.** A single seller account that represents a team, with automatic split-down to team members.
- **Royalty splits.** Secondary affiliate tiers, where the person who recruited the selling affiliate also earns a smaller share.
- **Protocol-owned revenue routes.** Splits that route directly to DAOs, treasuries, or multi-sig wallets as part of the transaction.

These are infrastructure primitives for the programmable commerce layer. The same mechanism that sends a commission to an affiliate will send a share to an AI agent, a DAO, or a RWA issuer as the system expands.

## What "instant" actually feels like

You make a sale. You see the USDC in your account balance within seconds. You can verify the Solana transaction signature. You can move the USDC to an exchange or hold it.

That is it. There is no payout step that runs later.

## What the fee looks like on-chain

The 3% fee routes to a LID-controlled address as part of the same transaction. It is visible on Solana and verifiable by anyone. There is no hidden second fee, no currency conversion markup, no processing fee added later. What you see on the product page is what settles.

Next: [The 3% fee →](the-3-percent-fee.md)
