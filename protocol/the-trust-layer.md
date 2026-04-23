# The trust layer

Trust in creator commerce is usually a spreadsheet. A platform tracks clicks, attributes sales, calculates commissions, holds the money, and sends payouts on a schedule. Every step is a database entry. Every step is contestable.

LID replaces that with a smart contract.

## What a trust layer actually is

A trust layer is the answer to three questions:

1. **Who drove this sale?** (Attribution)
2. **How much does each party get?** (Splits)
3. **When do they get it?** (Settlement)

On most platforms, all three are decided off-chain. Click logs attribute the sale. A commission engine calculates the split. A payout schedule determines when money moves. Every step involves the platform as an arbiter, and every step is a place where trust can break.

LID executes all three inside the Solana transaction that processes the sale. Attribution is bound when the buyer checks out. Splits are calculated by rules set at product creation. Settlement happens in the same transaction. No arbiter. No spreadsheet. No delay.

## Why the spreadsheet model breaks

The current creator commerce stack was built for advertisers buying ad inventory. It tracks clicks and reports attribution after the fact, then reconciles money later. That model works if you're Google selling ads. It breaks when you're a creator and an affiliate trying to share revenue.

Specific failure modes:

- **Attribution disputes.** Two affiliates claim the same sale. The platform picks one. Trust erodes.
- **Payout delays.** Money sits with the platform for 30 to 60 days. When the platform fails or changes policy, the money is exposed.
- **Commission changes.** A creator lowers the commission retroactively. The affiliate has no recourse.
- **Platform risk.** If the platform dies, all attribution data dies with it. Affiliates lose history.

## What on-chain enforcement changes

When attribution and splits are enforced by a smart contract:

- The split rule for a product is visible to every party before anyone shares it.
- The attribution for a sale is bound at the exact moment of checkout.
- The money moves in the same transaction as the sale.
- No party (including LID) can retroactively alter the split.
- Every sale, every split, every payout is independently verifiable on Solana.

The result is that "trust" stops being a policy and starts being a property of the system.

## What this means for each side

**For sellers:** Your commission terms are exactly what you published. Affiliates can see them before they sell. No disputes.

**For affiliates:** Your commission is enforced by code, not a database. You don't wait for a payout window. You don't trust a platform not to change policy.

**For buyers:** The checkout is a single atomic event. The product is delivered as part of the transaction. The money moves to the right places as part of the same event.

**For LID:** Our 3% is settled in the same transaction as everyone else's split. We don't hold balances. We don't touch your money between the sale and the payout. Our revenue is a split line, not a custody relationship.

## Why Solana

Three things had to be true at the same time to make this work. All three became real in the last 18 months.

1. **Stablecoin depth.** USDC on Solana has the liquidity to settle real commerce.
2. **Sub-second settlement.** Transactions confirm fast enough that checkout feels like software, not like waiting for a blockchain.
3. **UX that hides the chain.** The buyer never sees a wallet, a gas prompt, or a chain selector.

Solana is the chain where all three are simultaneously true at the scale LID needs.

Next: [Instant splits →](instant-splits.md)
