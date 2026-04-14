---
title: "insQuoteSingleRoot Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insquotesingleroot_lwc_611900.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# insQuoteSingleRoot Lightning Web Component

insQuoteSingleRoot Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# insQuoteSingleRoot Lightning Web Component

This component acts as a container for a root product and its child items.

This component contains additional components that let users add and modify insured parties, add and move coverages, change attribute values, and rate quotes.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)This component works for desktop and is mobile responsive.

[](https://help.salesforce.com/s?language=en_US)

Here's what it looks like in the user interface:

The **insQuoteSingleRoot** LWC displays:

1.  Icons for the product
    
2.  Product name
    
3.  Total premium
    
4.  Icon for the insured item
    
5.  Insured item name
    
6.  Insured item attributes
    
7.  Insured item deductible
    
8.  Insured item coverages
    

The UI also displays **Rate** if the quote is modified.

[](https://help.salesforce.com/s?language=en_US)

## What Users Can Do on this LWC

With insQuoteSingleRoot, users can:

-   Remove product
    
-   Remove insured items
    
-   Edit insured item attributes
    
-   Modify coverages
    
-   Rate the product
    

[](https://help.salesforce.com/s?language=en_US)

## What this LWC Does

**insQuoteSingleRoot** LWC is a child item of **insQuote** and serves as a container for a single root product. It contains the method and styles for the quote.

[](https://help.salesforce.com/s?language=en_US)

## Services Called by this LWC

**insQuoteSingleRoot** calls the following services:

-   **InsProductService:getInsuredItems**
    
-   **InsProductService:getInsuredItemSpec**
    
-   **InsQuoteService:getLineDetails**
    
-   **InsQuoteService: addInsuredItem**
    
-   **InsQuoteService:updateChildLine**
    
-   **InsQuoteService:priceRootItem**
    

[](https://help.salesforce.com/s?language=en_US)

## Other LWCs Used by this Component

**insQuoteSingleRoot** includes the following LWCs inside it:

-   **pubsub**
    
-   **insCreateVersion**
    
-   **insVersionHistory**
    
-   **insProductInstance**
    
-   **insRecordEditor**
    

Did this article solve your issue?

Let us know so we can improve!

YesNo