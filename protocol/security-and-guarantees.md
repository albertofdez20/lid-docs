# Security and guarantees

Trust is the product. This page lays out what we guarantee, how we protect against failure modes, and what's still in active hardening.

## What LID guarantees today

**Attribution is enforced by smart contracts.** Every sale binds the affiliate at the moment of checkout. The contract settles the split according to the rules set at product creation.

**Splits settle atomically.** The sale, the seller's share, the affiliate's share, and LID's fee all move in the same Solana transaction. No partial settlements.

**LID does not custody your funds.** Your account balance lives on-chain. We do not pool your funds with LID operating capital. You can verify every transaction independently.

**Past sales are immutable.** Once a split settles, the record is on Solana forever. No one can edit it retroactively, not even us.

**The 3% fee is transparent.** The fee amount on every sale is visible on-chain. No hidden markup, no currency conversion margin, no added line items at payout.

## What is still being earned

**Repeatability at scale.** LID launched on Solana mainnet on April 22, 2026. We are in active alpha validation. Commercial proof (repeat sellers, affiliate-led GMV, loop completion rates) is being earned now, not yet completed. We will not call the product beta or claim production maturity until the proof is there.

**Formal audit.** A full third-party smart contract audit is part of the post-raise engineering roadmap. The contracts have been designed and reviewed internally with security as a primary goal. External audit is next.

**Fraud controls.** Permissionless distribution means the protocol has to defend against abuse without gating participation. Fraud control is a top priority area for ongoing engineering.

## What counts as a red-light bug

A red-light bug is anything that breaks the core trust promise:

- Lost funds.
- Payment routed to the wrong account.
- Split calculated incorrectly.
- Failed product creation that still charges the seller.
- Misleading payout or attribution data shown to a user.

Any unresolved red-light bug blocks phase progression for the entire product. We will not move forward in the roadmap while trust is compromised.

If you hit one, email alberto@lid.pro immediately. Every red-light bug goes to the founder.

## What counts as an acceptable non-red bug

- A UI glitch.
- A dashboard number that's slow to refresh.
- A support case that takes longer than we'd like.

These are normal in alpha. We fix them as fast as we can and they don't block phase progression.

## Operational boundaries we enforce

**No fiat payments until USDC liquidity is proven.** Integrating a fiat off-ramp before the USDC layer is stable would create an off-chain dependency that weakens the trust guarantee. Fiat is on the roadmap, post-raise.

**No Web3 complexity exposed to end users.** Sellers and buyers never see wallets, chain names, or gas prompts. If something about the UX feels Web3, it's a bug.

**No retroactive split changes.** A commission set at product creation is locked for the sales that happen under that commission. Sellers can change commission going forward, not retroactively.

**No "beta" label until repeatability is earned.** This is a language choice that reflects the engineering discipline. We do not inflate narrative beyond what proof supports.

## What you should verify yourself

Every sale on LID produces a Solana transaction signature. You can paste it into a block explorer and see:

- The full transaction
- Every account that moved USDC
- The exact amounts
- The timestamp
- The signer

This is the auditability that makes the trust layer work. You don't have to trust LID's dashboard. The dashboard is a convenience. The chain is the source of truth.

## Reporting

Email alberto@lid.pro for:

- Security concerns (handled privately and immediately)
- Red-light bugs
- Attribution or payout inconsistencies
- Responsible disclosure of smart contract vulnerabilities

Every report gets a direct response from the founding team.

Next: [Developers →](../developers/overview.md)
