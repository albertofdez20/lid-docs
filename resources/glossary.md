# Glossary

Key terms used across LID docs.

## Active alpha validation

LID's current commercial maturity. Live on Solana mainnet, operationally real, commercial proof still being earned through completed loops. Distinct from beta, which we will not claim before repeatability is proven.

## Activated seller

A user who has created a product AND shared it live. Creation alone is not activation. Sharing the link is what turns an account into an active seller.

## Affiliate share

The percentage of GMV driven by affiliate links, as opposed to direct seller-to-buyer sales. A leading indicator of whether the affiliate flywheel is real.

## Agentic Commerce API

The roadmap developer surface that exposes LID's commerce primitives (product creation, attribution, splits) as API and SDK methods. Launches post-raise.

## Attribution

The on-chain record of which affiliate (if any) drove a given sale. Bound at the moment of checkout, enforced by the smart contract, immutable after.

## Blended ARPU

Weighted average revenue per active seller per year across the 3% transaction fee and Pro subscription revenue streams. Current target: $143/year.

## Bridge

Lid's fiat rails partner. Live in production. Handles fiat-to-digital-dollars on the buyer side and digital-dollars-to-fiat off-ramp for sellers and affiliates.

## Completed loop

A single sale where all five steps happen. Create → Share → Sale → Attribution correct → Funds route correctly → Payout settles. All five steps must complete for the loop to count. Partial completion is not a loop.

## Core loop

**Create → Share → Sell → Get paid.** The four-step sequence every feature serves. If a feature strengthens this loop, we build it. If it doesn't, we don't.

## Digital dollars (USDC)

US dollar stablecoin issued by Circle, fully backed 1:1 by cash and short-term US Treasuries. The native settlement asset on LID. One USDC is always one US dollar. "Digital dollars" is the user-facing term.

## GMV

Gross merchandise value. Total dollar volume transacted through LID. Measured cumulatively across completed sales.

## High-intent user

A user who completes signup, creates a product, shares a live link, starts a sale flow, returns after first visit, or submits meaningful post-use feedback. The behavioral signal that separates real users from passive signups.

## Instant payout

Settlement that happens in the same transaction as the sale, with no payout schedule, minimum balance, or withdrawal request.

## Mom Test session

A documented observed onboarding session with a real seller. The tester's behavior and verbatim quotes drive product decisions.

## Observed-session pressure-testing

Lid's pre-external-audit trust mechanism. Every alpha session is observed and reconciled against payout and attribution correctness.

## On-chain product registry

An immutable record that a product exists on Solana. One record per product, not one per unit sold.

## Ownership record

An on-chain entry that proves who owns or has access to a product. One per buyer, per product.

## Permissionless distribution

Any user can generate an affiliate link and earn commission on any product that has affiliate commission enabled. No approval process. No application. No contract.

## Power user

A seller with at least 2 completed loops and at least 1 repeat action. Power users are the proof that the system produces earning behavior, not just one-time usage.

## Privy

The embedded wallet and auth provider. Live in production since April 2026. Every Lid account is a Privy embedded wallet under the hood.

## Pro tier

A planned subscription tier at around $29 per month. Leads with creator-to-buyer communication tools (email, community). Adds analytics, custom branding, advanced attribution, and priority support. The 3% transaction fee stays unchanged.

## Proof of liquidity

The phase at which LID has produced measurable, repeatable earning behavior. Not yet reached. Current phase is earning it through alpha usage.

## Red-light bug

Lost funds, payment routed to the wrong account, incorrect split calculation, failed product creation that still charged the seller, or misleading payout or attribution data shown to a user. Any unresolved red-light bug blocks all phase progression until it's fixed.

## Repeat seller

A seller who completes at least one additional loop after the first clean loop. Distinct from a power user: repeat behavior is the leading indicator, power-user status is the compound effect.

## Solana

The blockchain LID runs on. Chosen for sub-second transaction finality, USDC liquidity, and sub-cent fees. LID runs on Solana. LID is not a Solana product.

## Split

The division of a sale's proceeds between the seller, affiliate (if any), and LID. Executed atomically in the same Solana transaction as the sale.

## The 3% fee

LID's flat infrastructure fee. Deducted as part of the atomic split, routed to a LID-controlled address in the same transaction as the sale. No hidden markups, no processing fees added later.

## Trust layer

The combination of on-chain attribution enforcement, atomic splits, and instant settlement that replaces the platform-as-arbiter model with contract-as-arbiter.

Next: [Language guide →](/resources/language-guide.md)
