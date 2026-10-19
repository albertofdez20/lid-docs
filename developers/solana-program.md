---
description: >-
  What the Lid program does on Solana: product registry, checkout routing,
  attribution binding, fee enforcement, pools, atomicity, and the security
  posture.
---

# The Solana program

In plain words: the program is the piece of code on Solana that moves the money. It is what makes every sale split correctly and land in seconds, without Lid ever holding the funds.

Lid runs on a Solana program that enforces product registration, attribution binding, and atomic settlement. This page describes the architecture at a conceptual level. Full interfaces, method signatures, and example code publish after the external review, once the public API stabilizes.

## What the program does

At the program level, Lid implements:

1. **Product registry.** On-chain record of a product's ID, price, seller address, sharer commission percentage, and delivery metadata reference.
2. **Checkout routing.** A method that accepts a buyer's USDC payment and routes it to the seller, the sharer, and Lid per the rules set on the product.
3. **Attribution binding.** The checkout method reads an optional share reference parameter and binds that address as the beneficiary of the sharer split for this specific sale.
4. **Fee enforcement.** The 3% fee is a hard-coded split in the settlement logic, routed to a Lid-controlled address.
5. **Pools.** For challenges and campaigns, a budget sits in a pool the funder controls until a result verifies; assignment and claims are recorded on the same public ledger.

## Atomicity

Every checkout is a single Solana transaction. Within that transaction:

* Buyer's USDC is moved out
* Seller's share is moved in
* Sharer's share is assigned to a vault that only the sharer can claim from (if applicable)
* Lid's fee is moved in
* Access metadata is emitted (event log)

If any step fails, the transaction reverts. No partial state exists where the buyer has paid without receiving the product, or where the seller has been paid and the sharer's share has not been assigned.

## What lives on-chain

* Product registry entries
* Every sale transaction
* Every split settlement
* Share attribution bindings
* Pool funding, assignments and claims
* Seller and sharer account balances (in USDC)

## What lives off-chain

* Product descriptions and rich metadata
* Delivery files (hosted or linked)
* User account email and authentication
* Dashboard UI state

Off-chain data is not a source of truth for money flow. It exists to make the experience usable.

## Upgradability

The program is designed for controlled upgrades during the alpha phase.

No upgrade can retroactively change the terms of past sales. Historical split records are immutable regardless of future program versions.

## Security posture

**Design principles applied:**

* Minimum viable program surface.
* Payments route straight to the seller and to Lid. A sharer's share goes to a vault that only that sharer can claim from, and a sale with a refund window waits in a hold that can only release to the seller or return to the buyer.
* The 3% fee on a sale is a protocol constant, not a setting anyone can change. The fee on challenge and campaign payouts is a setting only Lid can change, from 0% to 10%. It is 3% today.
* No administrative function can send user funds anywhere else. In a dispute over a held sale, our team can only release the money to the seller or return it to the buyer. If our team has not decided a dispute 14 days after the refund window ends, anyone can release the payment to the seller, so a held payment never stays frozen.
* All state-changing operations emit events for off-chain monitoring.

**Planned external review:**

* Formal review by a specialized Solana security firm. The criteria are already written down.
* Ongoing bug bounty once the public API is stable.

**Not in place today:**

* Third-party review report.
* Published bug bounty program.

We are transparent about what is and isn't done. During active alpha, every completed loop is reviewed for correctness.

## Responsible disclosure

If you find a vulnerability, email [hello@lid.pro](mailto:hello@lid.pro) with details. We respond quickly, fix privately when possible, and credit researchers who help. Please do not publicly disclose before giving us a reasonable window to address the issue.

## What developers can do today

Today, the program is reached through the Lid web app and the agent connection over MCP (see [Agents on Lid](../agents/)). Direct on-chain interaction is possible (the program is deployed and public). An SDK is being built.

The Agentic Commerce API (roadmap) will provide the developer surface for programmatic access.

Next: [Agentic Commerce API](agentic-commerce-api.md)
