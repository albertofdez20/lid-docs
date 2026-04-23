# Payouts and USDC

Payouts on LID happen in the same transaction as the sale. There is no payout schedule. There is no payout threshold. The money lands in your account the moment the buyer pays.

## How it works

Every sale on LID settles atomically. All four moves happen in the same Solana transaction, or none of them do.

1. Buyer sends payment
2. Seller receives their share
3. Affiliate receives their commission
4. LID receives the 3% fee

If any step fails, the whole transaction reverts and no one is charged. There is no scenario where the buyer pays and the seller does not receive their split.

## What you actually see

When you make a sale, your account balance goes up immediately. You can verify the transaction on Solana. You don't have to wait for a payout window, request a withdrawal, or hit a minimum balance.

The balance is held at an address associated with your account. Your funds are never pooled with LID's operating funds. You can view every transaction on-chain.

## Digital dollars (USDC)

All payouts on LID settle in USDC. USDC is a US dollar stablecoin issued by Circle, fully backed 1:1 by cash and short-term US Treasuries. One USDC is always one US dollar.

Think of it as digital dollars that move at internet speed. The balance you hold in your LID account is dollar-denominated. It does not fluctuate with crypto prices.

## Can I get paid in fiat

Today: no. All settlement is in digital dollars.

Post-raise: yes. A fiat off-ramp is on the roadmap. After the raise closes, we'll integrate with a payment provider that lets you convert your USDC balance to your local currency and transfer to a bank account. The specific partner will be announced when the integration is live.

For now, if you need fiat, you can send USDC to an exchange that supports USDC on Solana (Coinbase, Kraken, Binance, and others) and withdraw fiat from there. This is an extra step, and we know it. Fixing it is a priority after the raise.

## Security

Your account balance lives on Solana. LID does not custody your funds beyond the infrastructure layer. You can always verify your balance and transaction history on-chain.

The smart contracts that execute the splits have been designed and reviewed with security as a primary goal. A formal audit is part of the post-raise engineering roadmap.

## What if something goes wrong

If a payout ever fails or routes incorrectly, that's a red-light bug and our highest priority. Email alberto@lid.pro immediately. Any red-light bug blocks phase progression for the product until it's fixed. We take this seriously. Trust through execution is the core promise.

In the current alpha phase, every completed loop is reviewed for correctness.

Next: [FAQ for sellers →](faq.md)
