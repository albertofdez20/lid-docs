# Integrations

LID is designed to play well with the tools creators and developers already use. This page covers what integrates today, what's planned, and how to propose a new one.

## What integrates today

**Payment inputs**

- USDC on Solana (native)
- Fiat-to-USDC on the buyer side through a hosted payment partner (the buyer sees USD, settlement is USDC)

**Delivery targets**

- Direct file delivery (PDF, ZIP, video, any file type)
- URL-based delivery (Notion, Google Drive, YouTube, Discord, Telegram, any link)

**Social sharing**

- Affiliate links are plain URLs, so they work on every platform: Twitter, LinkedIn, Instagram, TikTok, Threads, email, newsletter, Discord, Telegram, community forums, blogs.

**Verification**

- Every sale produces a Solana transaction signature that can be verified on any block explorer.

## On the roadmap

**Fiat off-ramp.** Post-raise. Lets sellers and affiliates convert USDC directly to their local currency and transfer to a bank account. Provider TBD.

**Webhooks.** Real-time events delivered to a URL you control. Useful for:
- Triggering external CRM entries on product creation
- Running onboarding automation on sale
- Syncing to a data warehouse

**SDK (JavaScript, Python).** Client libraries for reading LID state and (where the signer allows) creating products or affiliate links programmatically.

**Embeddable checkout.** Drop-in checkout flow for sellers who want to run the product page on their own site.

**Tax and accounting.** Native exports for common accounting systems and tax software.

**CMS plugins.** WordPress, Ghost, Webflow plugins to create and manage LID products from inside a content tool.

## Integration principles we hold to

**Don't break the trust layer.** No integration is allowed to touch the money flow. External systems read state, receive events, or trigger actions, but settlement stays on-chain.

**Don't expose Web3 complexity.** Any integration LID endorses must preserve the abstracted UX. If an integration adds wallet prompts or chain selectors to the end-user flow, it's not on-brand.

**Don't add hidden fees.** Integration partners can charge their own fees visibly, on top of LID. They cannot skim LID's 3% or take commission from the seller's share without explicit disclosure.

## Proposing an integration

If you want to integrate LID with a product you're building, we want to hear from you. Especially if you're building:

- AI agent frameworks
- Creator toolkits (content platforms, newsletter tools, community platforms)
- Analytics or attribution tools
- Marketplaces or aggregators
- Crypto wallets or exchanges

Email alberto@lid.pro with:

1. What you're building
2. How you'd integrate LID
3. What API or event surface you'd need
4. Timeline

Selected partners get early API access and design input.

## Partnership posture

We do not do prestige partnerships for the sake of prestige. Every integration we endorse has to produce measurable benefit for sellers or affiliates. Big-partnership theater gets filtered out.

Lightweight, practical, measurable. That's the standard.

Next: [Vision →](../company/vision.md)
