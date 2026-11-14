# Awesome-Payment-Processing-Gateway

# Awesome Payment Processing Gateway

> A curated list of top Payment Processing Gateway platforms — both SaaS/Hosted commercial solutions and open-source alternatives for accepting payments, orchestrating providers, and managing billing infrastructure.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Stripe](#stripe)
  - [Adyen](#adyen)
  - [PayPal](#paypal)
  - [Checkout.com](#checkoutcom)
  - [Braintree](#braintree)
- [Open-Source Software](#-open-source-software)
  - [Hyperswitch](#hyperswitch)
  - [Kill Bill](#kill-bill)
  - [BTCPay Server](#btcpay-server)
  - [Bitcart](#bitcart)
  - [Lago](#lago)
  - [Polar](#polar)
  - [Open Payment Host](#open-payment-host)
  - [TPT Pay](#tpt-pay)
  - [GoiPay](#goipay)
  - [Zoneless](#zoneless)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Payment Processing Gateway platforms. These are not open-source but are included as reference points for feature comparison.

### Stripe
**Type:** Developer-first payments infrastructure with extensive API
Stripe is the most widely adopted developer-first payment platform, offering a unified API for accepting payments, managing subscriptions, and handling payouts across 135+ currencies. Its strength is the depth of its API, extensive documentation, and ecosystem of SDKs. It is the benchmark against which open-source alternatives like Hyperswitch and TPT Pay are measured [citation:6][citation:10].

### Adyen
**Type:** Enterprise payment platform with global acquiring
Adyen provides a single platform for accepting payments across online, in-person, and mobile channels, with direct connections to major card networks. It is positioned for enterprises wanting unified commerce and global reach with a single provider.

### PayPal
**Type:** Consumer-trusted payment gateway with broad reach
PayPal is the most recognized consumer payment brand, offering checkout, invoicing, and peer-to-peer payments across 200+ markets. It is often used alongside a primary gateway to capture consumers who prefer PayPal over entering card details directly.

### Checkout.com
**Type:** Enterprise gateway with intelligent acceptance
Checkout.com provides payment processing with AI-driven acceptance optimization, covering cards, digital wallets, and local payment methods. It is positioned for enterprises wanting granular control over authorization rates and cost optimization.

### Braintree
**Type:** PayPal-owned gateway with drop-in UI
Braintree (a PayPal service) provides card and digital wallet processing with SDKs for web and mobile. It is known for its Drop-in UI, which simplifies PCI compliance, and is often chosen by businesses already in the PayPal ecosystem.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Payment Processing Gateway tools. The open-source ecosystem spans **payment orchestration platforms**, **subscription billing engines**, **crypto payment processors**, and **billing infrastructure**.

### Hyperswitch
**Stack:** Rust | **License:** Apache-2.0
Hyperswitch (by Juspay) is the leading open-source **payment orchestrator**, with **43k+ GitHub stars** and active development [citation:10]. It connects multiple payment processors through a single API, enabling intelligent routing, revenue recovery, and cost observability across PSPs. It supports both SaaS and self-hosted deployment, is PCI-compliant, and includes reconciliation dashboards. The platform is positioned as a way to avoid vendor lock-in while optimizing authorization rates and processing costs. **Best for:** Businesses wanting to orchestrate multiple payment providers through a single integration, with control over routing logic and cost optimization.

### Kill Bill
**Stack:** Java / MySQL/MariaDB/PostgreSQL | **License:** Apache-2.0
Kill Bill is an open-source **subscription billing and payments platform** in production since 2010, released under Apache 2.0 [citation:14]. It provides subscriptions, usage billing, invoicing, and payments with a REST API and the **Kaui** admin UI. Payment plugins exist for Stripe, Braintree, Adyen, and others, with tax plugins for Kintsugi. It supports multi-tenant white-label billing and is described as providing the technical controls enterprises use to meet SOC 2 and PCI DSS requirements. **Trade-off:** It is a billing engine, not a pure payment gateway—you integrate a payment processor for actual card processing. **Best for:** Businesses wanting to own their subscription billing infrastructure without per-transaction fees, accepting the operational overhead of a Java/DB stack.

### BTCPay Server
**Stack:** .NET / C# / PostgreSQL | **License:** Open Source
BTCPay Server is the dominant **self-hosted, non-custodial Bitcoin payment processor** [citation:3]. It supports on-chain BTC and Lightning Network payments, with stores, invoices, a Point of Sale terminal, crowdfunding apps, and plugins for Litecoin, Liquid, and Monero. It integrates with Shopify, WooCommerce, and Magento, and provides a REST API. **Critical security note:** Versions before **2.4.2 (August 2026)** contained a vulnerability allowing unauthenticated attackers to fetch LND macaroon files and take over the node, with confirmed in-the-wild exploitation. The current release is **2.4.4** (September 2026) [citation:3]. **Best for:** Merchants wanting to accept Bitcoin and Lightning payments without a custodian, accepting the operational burden of running a node.

### Bitcart
**Stack:** Python | **License:** Open Source
Bitcart is a free and open-source self-hosted payment processor for **BTC, LTC, BCH, XMR, ETH, TRX, USDT, and more** [citation:13]. It provides a platform for merchants with an admin panel, store integration, and Docker packaging. It has 958+ GitHub stars and 86 releases, with the latest version 0.10.3.0 in March 2026 [citation:13]. **Best for:** Merchants wanting multi-crypto payment acceptance with a self-hosted management interface, accepting a Python-based stack.

### Lago
**Stack:** Ruby / PostgreSQL / Redis | **License:** AGPL-3.0
Lago is an open-source **metering and usage-based billing** platform, positioned as an alternative to Chargebee and Stripe Billing for usage pricing [citation:5]. It handles event ingestion, billable metrics, plans, and invoicing, and pushes invoices to Stripe, Adyen, or GoCardless for collection. It is not a payment gateway itself—it is the billing layer that calculates charges before collection. **Best for:** Usage-based and AI companies wanting open-source metering and invoicing with payment collection delegated to a gateway.

### Polar
**Stack:** (Check repository) | **License:** Open Source
Polar is a modern open-source payment infrastructure for digital products and SaaS, with built-in tax handling, automated benefits, and integrations [citation:5]. It has 5,811+ GitHub stars and is positioned as a comprehensive payment solution for digital businesses. **Best for:** Digital product and SaaS businesses wanting an integrated payments and billing solution with tax handling built in.

### Open Payment Host
**Stack:** Go | **License:** Open Source
Open Payment Host is a self-hosted payment host that provides subscription management, webhooks, and cancellation flows for **Stripe, Square, Razorpay, and PayPal** [citation:8]. It handles subscription status webhooks (cancelled, expired, suspended, refunded) and provides a hosted checkout flow. It is positioned for businesses wanting a lightweight, self-hosted layer over existing payment providers rather than a full gateway replacement. **Best for:** Businesses wanting self-hosted subscription management with webhook handling across multiple providers, accepting a Go stack.

### TPT Pay
**Stack:** Go / PostgreSQL / NATS | **License:** MIT
TPT Pay is an open-source, self-hostable **Stripe alternative** with a Stripe API v2024-06-20 compatible interface, an append-only double-entry ledger, and a `CardNetworkAdapter` interface that abstracts card network access [citation:6][citation:7]. It ships with a `SandboxAdapter` for testing, with `BankSponsorAdapter` or `DirectAcquiringAdapter` planned for production. The project also includes TPT Credit, a sovereign credit blockchain with 12,000 credits/person/year. **Important:** The card network adapter is not yet production-ready—you must plug in a real adapter. **Best for:** Developers wanting an MIT-licensed, Stripe-API-compatible payment API with a double-entry ledger, accepting that card network connectivity is not yet available out of the box.

### GoiPay
**Stack:** Go | **License:** Open Source
GoiPay is a lightweight **crypto payment processor microservice** written in Go, designed for creating and processing cryptocurrency invoices via gRPC [citation:4]. It supports XMR, BTC, LTC, ETH (with many ERC-20 tokens), and BNB (with many BEP-20 tokens). It is positioned as a microservice to integrate into larger projects rather than a standalone merchant platform. **Best for:** Developers wanting a lightweight gRPC-based crypto invoice microservice to embed in their own applications.

### Zoneless
**Stack:** (Check repository) | **License:** Apache-2.0
Zoneless is an open-source **Stripe alternative for stablecoins**, offering checkout, subscriptions, and marketplace payouts with a Stripe-compatible API [citation:12]. It is positioned for businesses wanting to accept stablecoin payments without fees, with a familiar API surface. **Best for:** Businesses wanting a Stripe-compatible API for stablecoin payments, accepting the crypto-native focus.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Card Processing | Subscription Billing | Crypto | Self-Hosted | Best For |
|----------|---------|-------|-----------------|----------------------|--------|-------------|----------|
| **Stripe** | Proprietary | Cloud | ✅ | ✅ | (Limited) | ❌ | Developer-first payments |
| **Adyen** | Proprietary | Cloud | ✅ | ✅ | ❌ | ❌ | Enterprise unified commerce |
| **Hyperswitch** | Apache-2.0 | Rust | ✅ (Orchestrator) | (Check) | ❌ | ✅ | Multi-PSP orchestration |
| **Kill Bill** | Apache-2.0 | Java/DB | (Via plugins) | ✅ Deep | (Plugins) | ✅ | Subscription billing engine |
| **BTCPay Server** | Open Source | .NET/Postgres | ❌ | ❌ | ✅ BTC/LN | ✅ | Bitcoin/Lightning payments |
| **Bitcart** | Open Source | Python | ❌ | ❌ | ✅ Multi-crypto | ✅ | Multi-crypto processor |
| **Lago** | AGPL-3.0 | Ruby/Postgres | ❌ | ✅ Usage metering | ❌ | ✅ | Usage-based billing |
| **Open Payment Host** | Open Source | Go | (Via providers) | ✅ Webhooks | ❌ | ✅ | Self-hosted sub management |
| **TPT Pay** | MIT | Go/Postgres | ⚠️ Adapter needed | (Check) | (TPT Credit) | ✅ | Stripe-compatible API |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Payment Processing Gateway that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem for **payment processing** is **fragmented by design**—no single project replicates Stripe's full breadth of card acquiring, fraud prevention, and global coverage. **Hyperswitch** is the strongest open-source option for orchestrating multiple payment providers through a single API [citation:10], **Kill Bill** is the most mature open-source subscription billing engine [citation:14], and **BTCPay Server** dominates non-custodial Bitcoin payments [citation:3]. For actual card acquiring as a merchant of record, commercial gateways remain the only practical option—open-source projects either orchestrate existing providers or handle crypto rails.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
