---
title: "Understand Reprice All in Insurance Quotes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_reprice_all_quotes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Understand Reprice All in Insurance Quotes

Understand Reprice All in Insurance Quotes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Understand Reprice All in Insurance Quotes

Recalculate pricing across all products in an insurance quote to produce accurate quote-level aggregates and pricing results.

In the standard Quote UI, you configure each product bundle independently using the Configurator. The Update Pricing action recalculates the price based only on the context of that specific product. For single-root quotes, this product-level pricing is sufficient. Multi-root quotes contain multiple independent products that contribute to shared financial totals. When pricing runs only at the product level, the quote lacks the full product context, which results in:

-   Incorrect aggregate amounts (premiums and taxes) on the quote record.
-   Failure to execute Quote Pricing Procedures that depend on values across multiple products.

Without Reprice All, quote-level aggregate amounts may remain incorrect even when individual products show valid pricing. Reprice All recalculates pricing across the full quote context and computes rolled-up values at the quote level.

## How Reprice All Works

Click the Reprice All button after completing configuration for all products in a multi-root insurance quote. The Reprice All action invokes the Insurance Quote Details (Get, Patch) API which evaluates the entire quote context rather than a single product bundle.

When you click Reprice All, the Insurance Quote Details (Get, Patch) API performs the following actions:

-   Executes pricing logic and recalculates pricing for all root products in the quote.
-   Updates aggregated quote-level standard premium amounts.
-   Updates the quote with accurate roll-up amounts and ensures all cross-product rules are applied.

Did this article solve your issue?

Let us know so we can improve!

YesNo