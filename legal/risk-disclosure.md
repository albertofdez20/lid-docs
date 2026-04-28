# Risk Disclosure

_Last updated: 23 April 2026._ _Operated by Lid Labs Technologies - FZCO (Trade Licence 65802, DIEZA, Dubai, UAE)._

{% hint style="warning" %}
**Read this before you use Lid.** Lid runs on the Solana blockchain. That comes with real risks. Transactions are final. Smart contracts can fail. USDC has its own issuer risk. Wallets can be stolen. Tax is your job. If any risk below is one you are not willing to accept, do not use the service.

This document is not legal, financial, or tax advice.
{% endhint %}

## 1. Who this applies to

This Risk Disclosure applies to every user of Lid — Creator, Affiliate, and Buyer — on `lid.pro` and `app.lid.pro`. By using the service you confirm you have read and understood the risks below and accept them.

## 2. Transactions on the Solana blockchain are final

Every payment, payout, and attribution event on Lid is executed by a smart contract on the Solana blockchain. Once a transaction is confirmed, it cannot be reversed, paused, or edited — by you, by the counterparty, or by Lid.

* Lid cannot undo a sale.
* Lid cannot claw back a payout.
* Lid cannot refund a transaction that was submitted by mistake or to the wrong address.

Refunds, where offered, are a second transaction initiated by the Creator. They are not a reversal of the original.

Before you confirm a transaction, check the amount, the wallet address, the product, and the split.

## 3. Smart contract risk

Lid's smart contracts are deployed on the Solana mainnet. The code is audited, monitored, and continuously tested. Smart contracts can still have bugs, vulnerabilities, or edge cases that only surface under specific conditions.

Possible outcomes:

* A transaction fails and your gas fee is not refunded.
* A split executes in a way that differs from the user interface because of unexpected contract behaviour.
* A contract is paused by Lid's incident response process after a vulnerability is found.
* A contract is upgraded or migrated, and funds routed through prior versions behave differently.

Lid is not liable for losses caused by a bug, exploit, or upgrade of a smart contract, except to the extent required by mandatory law.

## 4. Solana network risk

Solana is a public, permissionless blockchain operated by a decentralised network of validators. Lid does not control it.

Network-level events that can affect you:

* **Congestion** — during peak demand, transactions can be delayed or dropped. A payment may fail even if your wallet has the funds.
* **Outages** — the Solana network has had outages in the past. While an outage is ongoing, no transactions can settle.
* **Fork or chain reorganisation** — in rare cases, the chain state may re-organise. Transactions confirmed in a short window could be affected.
* **Validator changes** — changes to validator behaviour, protocol upgrades, or consensus rules can change how transactions work.
* **Fee spikes** — network fees (gas) are paid in SOL and can rise sharply under load. You are responsible for having enough SOL in your wallet to pay them.

Lid does not guarantee that the Solana network will be available, performant, or secure at any given moment.

## 5. USDC and stablecoin risk

All settlements on Lid are in USDC — the US-dollar-pegged stablecoin issued by Circle Internet Financial, Inc. USDC is not issued or controlled by Lid.

Risks specific to USDC:

* **Peg risk.** USDC is designed to stay at approximately one US dollar per token. It has depegged in the past and can depeg again under market stress. When the peg slips, the value of your USDC balance in dollar terms slips with it.
* **Issuer risk.** Circle manages the reserves that back USDC. If Circle becomes insolvent, faces regulatory action, or changes the redemption rules, USDC holders may face losses or delays.
* **Blacklisting.** Circle can, under some conditions, freeze or blacklist wallet addresses tied to sanctioned persons, fraud, or regulator action. A blacklisted wallet loses access to USDC balances.
* **Bridge risk.** Lid only accepts native Solana USDC. If you send bridged or wrapped USDC from another chain, the transaction may fail or land in a state Lid cannot recover.
* **Regulatory change.** Stablecoin regulation is evolving in many jurisdictions. Future rules may affect your ability to hold, send, or receive USDC.

Read Circle's terms and disclosures at `circle.com/en/legal` before using Lid.

## 6. Wallet and self-custody risk

Lid is non-custodial. You hold your own private keys, either directly in an external wallet (for example, Phantom, Solflare, Backpack) or through an embedded wallet provider such as Privy.

What this means:

* If you lose your private key or recovery phrase, your funds are gone. No one — not Lid, not the wallet provider, not Solana — can recover them.
* If your key is stolen, the thief can move your funds. Lid cannot freeze or reverse transactions signed with your key.
* If you approve a malicious transaction, by mistake or through a phishing attack, the damage is permanent.

Protect your keys. Check every transaction before you sign. Do not sign messages you do not understand. Verify domains before connecting your wallet.

If you use Privy or a similar embedded wallet, that provider's security model and terms apply to how your keys are generated, stored, and recovered. Lid does not control those arrangements.

## 7. Transaction and attribution risk

Lid's smart contract enforces attribution at the moment of sale. Attribution depends on the referral code present in the transaction.

Possible outcomes:

* **Last-touch attribution.** A Buyer who clicks multiple affiliate links before checkout is typically attributed to the last valid referral carried at checkout. This logic is published in our documentation and may change over time.
* **Unattributed sales.** If a Buyer lands on the product without a referral parameter, the Creator keeps the share that would otherwise go to an Affiliate. Affiliates earn commission only when attribution is present.
* **Self-referrals and abuse.** Affiliates who attempt to self-refer, farm fake traffic, or manipulate attribution may be disabled. Commissions earned through abuse may be held, reversed where possible, or reported to authorities.
* **Attribution windows.** Attribution is tied to the transaction, not a cookie window. There is no retroactive commissioning and no lookback period for sales that did not carry a referral at checkout.

Lid does not guarantee any specific affiliate conversion rate or any volume of attributed sales.

## 8. Product delivery is between Creator and Buyer

Lid routes payments and attribution. Lid does not:

* Host, warrant, or certify the content of the products sold.
* Guarantee that the product delivered matches the description.
* Handle refunds or chargebacks between Creator and Buyer.
* Arbitrate disputes about product quality.

If you are a Buyer, read the product description, preview, and the Creator's own refund policy before paying. If you are a Creator, write an accurate description and honour your stated terms.

Lid may suspend or remove a Creator's account for repeated or serious misrepresentation, as described in the [Terms of Service](terms.md).

## 9. Price and market risk

USDC is designed to track the US dollar, not your local currency. If you are exposed to a different home currency, the value of a USDC balance in that currency will move with the USD/home-currency exchange rate.

Creators setting prices in USDC should understand that their local-currency revenue is exposed to currency movement. Buyers paying in USDC should understand that the local-currency cost is exposed to the same movement.

Lid does not hedge currency risk for you.

## 10. Regulatory and legal risk

The legal status of digital assets, stablecoins, affiliate marketing, and blockchain-based commerce varies by jurisdiction and is changing.

Possible outcomes:

* A jurisdiction restricts or bans the use of USDC or non-custodial wallets, making Lid unavailable there.
* A regulator introduces new obligations — for example, VAT collection, consumer refund rules, or affiliate disclosure rules — that apply to your activity on Lid.
* A court order or regulator action requires Lid to suspend accounts, freeze referrals, or disclose user data.

You are responsible for knowing the rules in your jurisdiction and for complying with them. If you are unsure, seek local legal advice before using Lid.

Lid currently operates from Dubai, UAE. Our licensing authority is the Dubai Integrated Economic Zones Authority. We follow the sanctions regimes of the UN, the US, the EU, the UK, and the UAE, and we do not serve comprehensively sanctioned countries or sanctioned persons.

## 11. Tax risk and responsibility

Lid does not withhold tax from your payouts. Lid does not file tax returns on your behalf. Lid does not give tax advice.

You are responsible for:

* Classifying transactions correctly under the tax rules of your jurisdiction.
* Reporting and paying income tax, corporate tax, VAT or sales tax, and any other tax that applies.
* Keeping records of your Lid activity for the retention period the law requires.

Crypto-to-fiat conversions, stablecoin receipts, and affiliate commissions are often taxable events. Tax rules for digital assets change. Seek advice from a qualified tax professional in your jurisdiction.

## 12. Counterparty and fraud risk

Lid brings together Creators, Affiliates, and Buyers who may never meet. Even with on-chain attribution and instant settlement:

* A Creator may ship a product that is different from the description.
* An Affiliate may use questionable traffic sources.
* A Buyer may dispute a purchase outside the Lid system, for example by filing a complaint with a regulator.

Use your judgment. Preview products. Read the Creator's reputation signals. Start small before spending large amounts.

## 13. Third-party service risk

Lid relies on third-party services to run the platform. Outages, security incidents, or changes at these providers can affect Lid.

Providers you should be aware of:

* **Privy** — wallet creation and authentication (Stripe-owned since June 2025).
* **Alchemy** — Solana RPC.
* **Pinata** — IPFS storage for product files and metadata. IPFS is a distributed storage network. If pinning is lost, a file may become temporarily unavailable.
* **Helius** — transaction monitoring and webhooks.
* **Circle** — USDC issuer.

See the [Privacy Policy](privacy.md) for the full list and links to each provider's terms.

## 14. Phishing, scams, and social engineering

Attackers frequently target crypto users with fake sites, fake support requests, and malicious links.

Rules of thumb:

* Lid will never ask for your private key or recovery phrase. No one from Lid will ever need it.
* The only official domains are `lid.pro` and `app.lid.pro`. Check the URL every time.
* If a "Lid employee" asks you to sign a transaction, it is not Lid.
* If a deal sounds too good to be true, it is.

Report anything suspicious to `security@lid.pro`.

## 15. No investment or professional advice

Nothing on Lid — product pages, marketing pages, or internal messaging — is investment advice, legal advice, financial advice, or tax advice. Products listed on Lid are not securities offerings and are not registered as such. Creators are solely responsible for the compliance of their products.

If you need advice, talk to a qualified professional licensed in your jurisdiction.

## 16. Changes to this Disclosure

We may update this document as Lid evolves and as the risks change. When we do, we update the "Last updated" date at the top and post the new version on this page.

## 17. Contact

**Lid Labs Technologies - FZCO** IFZA Business Park, DDP PO Box 342001, Dubai, United Arab Emirates Email: legal@lid.pro
