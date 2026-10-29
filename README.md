# Awesome-Cross-Border-E-Commerce

# Top Cross-Border E-commerce Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on International Checkout, Duty Calculation & Self-Hosted Global Store Infrastructure*  
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Cross-Border E-commerce**. These tools enable merchants to sell internationally by localizing pricing, calculating duties and taxes, offering local payment methods, and navigating customs compliance—removing the friction that prevents global shoppers from completing purchases.

**Examples** include Shopify Markets, Global-e, Borderfree, Flow Commerce, ESW (eShopWorld), Glopal, Zonos, FlavorCloud, Reach, and Passport Global (the category leaders).

**Open-source emphasis**: Cross-Border E-commerce is a domain where open-source tooling is **fragmented and largely insufficient for the full cross-border stack**. The strongest active projects are **WooCommerce Customs Fees** (a GPL plugin adding transparent duty calculation to checkout) , **Price Based on Country for WooCommerce** (a free plugin for geolocation-based pricing and multi-currency) , and **Prism** (a Next.js reference implementation for PPP pricing and AI localization) . For landed cost calculation as a service, **POTAL MCP Server** provides an API-backed tool with 240 countries and 257M+ tariff records—but it requires an external API key and is not fully self-contained . **No open-source project replicates the merchant-of-record, guaranteed duty coverage, and fraud protection** of Shopify Markets Pro (powered by Global-e) or the end-to-end localization of Global-e .

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Shopify Markets](https://www.shopify.com/markets)**  
  Shopify's native cross-border toolkit for creating regional markets with localized currencies, domains, languages, and pricing adjustments; handles duties and taxes configuration at checkout, though full merchant-of-record compliance requires Markets Pro .

- **[Shopify Markets Pro](https://help.shopify.com/en/manual/markets/markets-pro/overview)**  
  Powered by **Global-e** as merchant of record; takes care of local tax registration, duty calculation, international shipping, and fraud management with **guaranteed duty and tax amounts at checkout** (covers customs differences) . Pricing: **6.5% per transaction** (includes payment processing) plus **2.5% currency conversion fee**; no monthly fee, cancel anytime . Not compatible with B2B orders .

- **[Global-e](https://www.global-e.com/)**  
  Leading end-to-end cross-border solutions provider (NASDAQ: GLBE) and the engine behind Shopify Markets Pro; supports 200+ destinations, 100+ currencies, 150+ local payment methods, 26 languages, local duty/tax calculation, fraud protection, and returns . Net Dollar Retention above 125% since 2018; merchants include Marc Jacobs (130% YoY international revenue increase) and Native Shoes (76% conversion increase) .

- **[Borderfree](https://www.borderfree.com/)**  
  Cross-border ecommerce solution (now part of Global-e) providing international checkout localization, duty/tax calculation, and shipping for enterprise retailers.

- **[Flow Commerce](https://www.flow.io/)**  
  Cross-border commerce platform with localization, duty/tax calculation, and international payment methods; focused on mid-market and enterprise merchants.

- **[ESW (eShopWorld)](https://www.esw.com/)**  
  Direct-to-consumer cross-border ecommerce provider with localized checkout, duty/tax handling, and logistics for global brands.

- **[Glopal](https://www.glopal.com/)**  
  Cross-border localization platform with translated storefronts, multi-currency pricing, and duty/tax calculation for international shoppers.

- **[Zonos](https://zonos.com/)**  
  AI-powered cross-border operating system with **HS code classification** (reads product images, predicts country of origin, detects undervalued shipments) , duty/tax calculation, localized checkout (30+ currencies, 15+ languages), fraud protection, and carrier integration . 16+ years of trade data, 200+ supported countries, 200,000+ orders per day. Customers report 70% reduction in customer service complaints after implementation .

- **[FlavorCloud](https://www.flavorcloud.com/)**  
  Cross-border shipping and compliance platform with duty/tax calculation, HS code classification, and carrier network integration.

- **[Reach](https://www.reach.com/)**  
  Cross-border payments and localization platform with multi-currency processing and local payment method support.

- **[Passport Global](https://www.passportglobal.com/)**  
  International shipping and compliance platform with duty/tax calculation, carrier management, and customs documentation.

## Open-Source GitHub Projects

### WooCommerce Plugins

- **[WooCommerce Customs Fees](https://github.com/woocommerce/customs-fees-for-woocommerce)**  
  Official WooCommerce plugin (GPL) adding **transparent customs and import fee calculations** to checkout . Creates a rules table for country-level duty and fee configuration; supports **CIF (Cost, Insurance, Freight) calculations** with optional insurance value filters; integrates with multi-currency plugins; caches calculations per session for performance (<50ms average) . **Critical caveat**: fees are for **display transparency only**—actual collection depends on your payment gateway and business model; most merchants show fees but collect separately at customs . Version 1.3.0 (June 2026) updated China-to-US tariff rates after IEEPA tariffs were struck down .

- **[Price Based on Country for WooCommerce](https://wordpress.org/plugins/woocommerce-product-price-based-on-countries/)**  
  Free WordPress.org plugin (100% free core) for **country-specific pricing and multi-currency** . Features geolocation-based price display, manual fixed prices per country/region or automatic exchange rate conversion, country switcher widget, and multilingual compatibility (WPML, Polylang) . PRO adds automatic exchange rate updates, price rounding ("pretty prices"), and bulk CSV import . **The most practical free foundation for localized pricing** on WooCommerce, though it does not handle duty calculation or customs compliance.

### Reference Implementations & Demos

- **[Prism](https://github.com/CoderOtakuX/Prism)**  
  Open-source **"Link-in-Bio" global store** demonstrating automatic language and price adaptation based on visitor location (Next.js 15, Supabase, Lingo.dev, Vercel) . Features **auto-location detection**, **PPP (Purchasing Power Parity) pricing** to adjust affordability by region, and **AI localization** via Lingo.dev for on-the-fly translation without manual JSON files . **A working reference for PPP pricing and AI-driven localization**, but it is a demo store, not a production cross-border platform with duty/tax/customs handling .

### Landed Cost & Tariff APIs

- **[POTAL MCP Server](https://socket.dev/npm/package/potal-mcp-server)**  
  MCP server for **landed cost calculation** across 240 countries, with 257M+ tariff records, 131K government tariff schedules, 1.36M product-HS mappings, 63 FTAs, and sanctions screening (21K+ entries) . Tools include `calculate_landed_cost`, `classify_product` (GRI Pipeline, 592 codified rules), `check_restrictions`, `screen_denied_party`, `lookup_fta`, and document generation (Commercial Invoice, Packing List, Certificate of Origin) . **Requires a POTAL API key** (external service)—not fully self-hosted, but provides the most comprehensive tariff data available as an API wrapper .

- **[mcp-logistics](https://github.com/zavora-ai/mcp-logistics)**  
  Open-source MCP server (Apache-2.0) with 16 tools across ShipEngine, Shippo, and Google Maps backends for **multi-carrier rate comparison, tracking, label generation, address validation, and route optimization** . **Shipping-focused** rather than duty/tax—useful as the fulfillment layer of a cross-border stack, but requires carrier API credentials .

### Additional Strong Open-Source Options

- **Openfront** — Open-source Shopify alternative (Next.js/KeystoneJS) with **multi-region deployment support**, localized payments, multi-currency pricing, and regional tax/compliance tools . Self-hostable with Stripe/PayPal integrations . **Full e-commerce platform** rather than a cross-border add-on—provides the foundation for building a global store, but duty/tax calculation requires configuration or third-party integration .
- **No mature open-source merchant-of-record equivalent exists** — The legal and tax infrastructure of Global-e or Shopify Markets Pro (tax registration, guaranteed duty coverage, fraud liability) requires banking relationships and regulatory compliance that open-source cannot replicate .

**Frameworks for building custom systems**: For **WooCommerce stores**, combine **Price Based on Country** for localized pricing  with **Customs Fees** for duty display . For **PPP pricing and AI localization**, **Prism** provides a working reference pattern . For **landed cost calculation as a service**, **POTAL MCP Server** offers the most comprehensive tariff data via API . For **shipping and fulfillment**, **mcp-logistics** provides multi-carrier rate comparison . No open-source project delivers the full merchant-of-record experience—organizations requiring guaranteed duty coverage and tax remittance should evaluate Shopify Markets Pro or Global-e.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Cross-border e-commerce platforms handling international transactions must comply with customs regulations, tax laws (VAT/GST/duty), and data privacy requirements in every jurisdiction of operation; **incorrect duty calculation or customs documentation can result in shipment delays, fines, or seizure**.
- **Open-source cross-border e-commerce is fragmented across pricing, duty display, and shipping layers**—WooCommerce plugins provide localized pricing and duty estimation , Prism demonstrates PPP pricing , and POTAL provides tariff data via API . However, **no open-source project replicates the merchant-of-record, guaranteed duty coverage, and tax remittance** of Shopify Markets Pro or Global-e . Merchants requiring full cross-border compliance should evaluate commercial platforms.
- Verify license terms for commercial use; WooCommerce Customs Fees and Price Based on Country are GPL , Prism is open-source (check repository) , and POTAL MCP Server requires a paid API key .

---

**Made for ecommerce merchants, international expansion teams, and cross-border platform engineers.**  
Let's make cross-border e-commerce more open, but with clear eyes about the merchant-of-record and tax-remittance infrastructure that software alone cannot replace.
