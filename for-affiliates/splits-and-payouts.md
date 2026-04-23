# Splits and payouts

The split is the transaction. There's no payout step that happens after.

## The mechanic

When a buyer checks out through your affiliate link, the smart contract executes a single Solana transaction that does four things at once:

1. Accepts the buyer's payment in USDC
2. Sends the seller's share to the seller's account
3. Sends your commission to your account
4. Sends the 3% infrastructure fee to LID

If any of those steps fails, the whole transaction reverts. The buyer isn't charged. The seller doesn't get paid. You don't either. There is no scenario where the money gets stuck in limbo.

## What you receive

The commission percentage set on the product when you generated your link. Example: if the commission is 25% and the sale price is $200, you receive $50 in USDC the moment the transaction clears.

The percentage cannot be changed retroactively. The rate at the moment of sale is the rate that applies.

## Where the money lands

Your balance sits in your LID account, associated with a Solana address. You can verify it on-chain anytime. LID does not custody your funds in a pooled treasury. They're yours, on-chain, addressable by you.

## Seeing your payouts

Your dashboard shows every split you've received with:

- Date and time
- Product
- Sale amount
- Your percentage
- Your USDC amount
- Solana transaction signature (clickable, opens the on-chain record)

Every payout is independently verifiable on a block explorer.

## Off-ramping to fiat

Today: you can move USDC from your LID account to any exchange that supports USDC on Solana (Coinbase, Kraken, Binance, others), convert to fiat there, and withdraw to your bank.

Post-raise: a fiat off-ramp will be integrated directly. You'll be able to convert USDC to your local currency and transfer to a bank account without leaving LID. The provider will be announced when the integration is live.

## What if a sale gets refunded

If the seller issues a refund, the split reverses. Your commission is returned along with the seller's share. This is deliberate and symmetric. Your commission is tied to the sale actually sticking.

Refund policies are set per seller. Check the product page if you want to understand a seller's policy before sharing.

## Disputes

Attribution is enforced by the smart contract. If you drove the checkout, you're paid. There is no "contested commission" workflow because there's nothing to contest. The contract has already settled.

If something goes wrong at a protocol level (a payment routed to the wrong account, a split calculated incorrectly), that's a red-light bug. Email alberto@lid.pro. Any red-light bug blocks phase progression until it's resolved.

## Tax

LID does not withhold taxes. Commissions are your income. You're responsible for reporting them according to your local tax obligations. The dashboard can export transaction history for accounting.

Next: [Best practices →](best-practices.md)
