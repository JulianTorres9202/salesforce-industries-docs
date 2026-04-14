---
title: "insQuote Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquote_lwc.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# insQuote Lightning Web Component

insQuote Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# insQuote Lightning Web Component

Use this component to display a quote. Calling other Lighting web components, insQuote, called **Vlocity Insurance Quote** in the Lightning App Builder, displays root products, coverages, insured items, insured parties, and attributes.

This component contains additional components that let users add and modify insured items, add and modify insured parties, add and remove coverages, change attribute values, and reprice the quote based on changes made.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)This component works for desktop and is mobile responsive.

To start off, **insQuote** displays the option to select the product being quoted. Here's what it looks like:

After a product is selected, the subsequent options are introduced based on the product structure. Here's an example of what it could look like after selecting a product:

When it's been populated with information, **insQuote** LWC also displays:

[](https://help.salesforce.com/s?language=en_US)

1.  Icon for the product
    
2.  Product name
    
3.  Total Premium
    
4.  Icon for the insured item
    
5.  Insured item name
    
6.  One or more insured item attributes
    
7.  Insured item deductible
    
8.  Insured Item
    

The LWC also displays **Rate** if the quote has been modified.

[](https://help.salesforce.com/s?language=en_US)

## What Users Can Do on this LWC

With the top-level **insQuote** LWC, users can:

-   Add products
    

When a product is added, **insQuote** acquires child LWCs. After this, **insQuote** can be used to:

[](https://help.salesforce.com/s?language=en_US)

-   Add insured items
    
-   Add or remove coverages
    
-   Modify coverage attributes
    
-   Edit insured items
    
    Look for the pencil icon.
    
-   Delete products
    
    Look for the trashcan icon.
    
-   Delete insured items
    
    Look for the trashcan icon.
    

[](https://help.salesforce.com/s?language=en_US)

## What this LWC Does

The **insQuote** LWC is a container for the quote product list. It fetches the Quote line items and displays them as a list on the page.

If there are no products added, **insQuote** adds the root products to the page as the user builds the quote from scratch.

[](https://help.salesforce.com/s?language=en_US)

## Services Called by this LWC

**insQuote** doesn't call any services.

[](https://help.salesforce.com/s?language=en_US)

## Other LWCs Used by this Component

**insQuote** includes these components:

-   **lodash**
    
-   **pubsub**
    
-   **utility**
    
-   **date\_fns**
    
-   **insCreateVersion**
    
-   **insPolicyManagement**
    
-   **insQuoteSingleRoot**
    
-   **insQuoteLargeGroup**
    
-   **insQuoteProductList**
    

Did this article solve your issue?

Let us know so we can improve!

YesNo