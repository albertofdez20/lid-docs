# Smart contracts

LID runs on a Solana program that enforces product registration, attribution binding, and atomic settlement.

This page describes the architecture at a conceptual level. Full ABIs, method signatures, and example code publish when the contracts are audited and the public API stabilizes.

## What the program does

At the contract level, LID implements:

1. **Product registry.** On-chain record of a product's ID, price, seller address, affiliate commission percentage, and delivery metadata reference.
2. **Checkout routing.** A method that accepts a buyer's USDC payment and routes it to the seller, affiliate, and LID per the rules set on the product.
3. **Attribution binding.** The checkout method reads an optional affiliate reference parameter and binds that address as the beneficiary of the affiliate split for this specific sale.
4. **Fee enforcement.** The 3% fee is a hard-coded split in the settlement logic, routed to a LID-controlled address.

## Atomicity

Every checkout is a single Solana transaction. Within that transaction:

- Buyer's USDC is moved out
- Seller's share is moved in
- Affiliate's share is moved in (if applicable)
- LID's fee is moved in
- Access metadata is emitted (event log)

If any step fails, the transaction reverts. No partial state exists where the buyer has paid but not received the product, or where the seller has been paid but the affiliate hasn't.

## What lives on-chain

- Product registry entries
- Every sale transaction
- Every split settlement
- Affiliate attribution bindings
- Seller and affiliate account balances (in USDC)

## What lives off-chain

- Product descriptions and rich metadata
- Delivery files (hosted or linked)
- User account email and authentication
- Dashboard UI state

Off-chain data is not a source of truth for money flow. It exists to make the experience usable.

## Upgradability

The current contracts are designed for controlled upgradability during the alpha phase. Upgrade authority is governed by a multi-sig and will transition to a decentralized governance model as the protocol matures.

No upgrade can retroactively change the terms of past sales. Historical split records are immutable regardless of future contract versions.

## Security posture

**Design principles applied:**

- Minimum viable contract surface.
- Payments always route directly to recipient accounts, never through intermediate holding accounts.
- The 3% fee is enforced as a protocol constant, not a mutable config field.
- No administrative function can move user funds.
- All state-changing operations emit events for off-chain monitoring.

**Planned external review:**

- Formal audit by a specialized Solana security firm (post-raise).
- Ongoing bug bounty once the public API is stable.

**Not yet in place:**

- Third-party audit report.
- Published bug bounty program.

We are transparent about what is and isn't done. During active alpha, every completed loop is reviewed for correctness.

## Responsible disclosure

If you find a vulnerability, email alberto@lid.pro with details. We respond quickly, fix privately when possible, and credit researchers who help. Please do not publicly disclose before giving us a reasonable window to address the issue.

## What developers can do today

Today, contract interaction happens through the LID web app. Direct on-chain interaction is possible (the contracts are deployed and public), but there is no published SDK or client library yet.

The Agentic Commerce API (roadmap, post-raise) will provide the developer surface for programmatic access.

Next: [Agentic Commerce API →](agentic-commerce-api.md)
