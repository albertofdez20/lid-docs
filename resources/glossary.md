# Glossary

Key terms used across LID docs.

## Core loop

**Create → Share → Sell → Get paid.** The four-step sequence every feature serves. If a feature strengthens this loop, we build it. If it doesn't, we don't.

## Completed loop

A single sale where all five steps happen. Create → Share → Sale → Attribution correct → Funds route correctly → Payout settles. All five steps must complete for the loop to count. Partial completion is not a loop.

## Activated seller

A user who has created a product AND shared it live. Creation alone is not activation. Sharing the link is what turns an account into an active seller.

## Power user

A seller with at least 2 completed loops and at least 1 repeat action. Power users are the proof that the system produces earning behavior, not just one-time usage.

## Repeat seller

A seller who completes at least one additional loop after the first clean loop. Distinct from a power user: repeat behavior is the leading indicator, power-user status is the compound effect.

## Red-light bug

Lost funds, payment routed to the wrong account, incorrect split calculation, failed product creation that still charged the seller, or misleading payout or attribution data shown to a user. Any unresolved red-light bug blocks all phase progression until it's fixed.

## High-intent user

A user who completes signup, creates a product, shares a live link, starts a sale flow, returns after first visit, or submits meaningful post-use feedback. The behavioral signal that separates real users from passive signups.

## Blended ARPU

Weighted average revenue per active seller per year across the 3% transaction fee and Pro subscription revenue streams. Current target: $143/year.

## GMV

Gross merchandise value. Total dollar volume transacted through LID. Measured cumulatively across completed sales.

## Affiliate share

The percentage of GMV driven by affiliate links, as opposed to direct seller-to-buyer sales. A leading indicator of whether the affiliate flywheel is real.

## Attribution

The on-chain record of which affiliate (if any) drove a given sale. Bound at the moment of checkout, enforced by the smart contract, immutable after.

## Split

The division of a sale's proceeds between the seller, affiliate (if any), and LID. Executed atomically in the same Solana transaction as the sale.

## Instant payout

Settlement that happens in the same transaction as the sale, with no payout schedule, minimum balance, or withdrawal request.

## Digital dollars (USDC)

US dollar stablecoin issued by Circle, fully backed 1:1 by cash and short-term US Treasuries. The native settlement asset on LID. One USDC is always one US dollar. "Digital dollars" is the user-facing term.

## Solana

The blockchain LID runs on. Chosen for sub-second transaction finality, USDC liquidity, and sub-cent fees. LID runs on Solana. LID is not a Solana product.

## The 3% fee

LID's flat infrastructure fee. Deducted as part of the atomic split, routed to a LID-controlled address in the same transaction as the sale. No hidden markups, no processing fees added later.

## Pro tier

A planned subscription tier (~$29/month) that unlocks analytics, custom branding, and priority support. Does not exist today. Will launch when features justify it.

## Agentic Commerce API

The roadmap developer surface that exposes LID's commerce primitives (product creation, attribution, splits) as API and SDK methods. Launches post-raise.

## Proof of liquidity

The phase at which LID has produced measurable, repeatable earning behavior. Not yet reached. Current phase is earning it through alpha usage.

## Active alpha validation

LID's current commercial maturity. Live on Solana mainnet, operationally real, commercial proof still being earned through completed loops. Distinct from beta, which we will not claim before repeatability is proven.

## Permissionless distribution

Any user can generate an affiliate link and earn commission on any product that has affiliate commission enabled. No approval process. No application. No contract.

## Trust layer

The combination of on-chain attribution enforcement, atomic splits, and instant settlement that replaces the platform-as-arbiter model with contract-as-arbiter.

Next: [Language guide →](language-guide.md)
