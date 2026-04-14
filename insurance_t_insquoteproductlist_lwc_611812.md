---
title: "insQuoteProductList Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insquoteproductlist_lwc_611812.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# insQuoteProductList Lightning Web Component

insQuoteProductList Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# insQuoteProductList Lightning Web Component

This component shows the list of eligible products that can be added to start building the quote.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)This component works for desktop and is mobile responsive.

[](https://help.salesforce.com/s?language=en_US)

Here's what it looks like in the user interface.

The **insQuoteProductList** LWC displays:

1.  A search field
    
2.  **Product Name** with **Product Family**, **Line of Business** and **Type**.
    
    Users can customize this from the **Custom Settings**.
    
3.  **Add**, **Reset**, and **Cancel** buttons
    
4.  **Next** and **Previous** buttons
    

[](https://help.salesforce.com/s?language=en_US)

## What Users Can Do on this LWC

-   View the complete list of available products.
    
    Use the **Next** and **Previous** buttons to navigate the list
    
-   Customize the columns in this modal.
    
    To customize columns, navigate to **Product List: Custom Settings** > **Mange Insurance Configuration Setup** > **Edit ProductSearchFields** > **Add Product fields in Setup Value**.
    
-   Search for a product.
    
-   Select one or more products to add to a quote.
    
-   Add products to a quote.
    
-   Undo currently selected products.
    
-   Close the modal.
    

[](https://help.salesforce.com/s?language=en_US)

## What this LWC Does

-   Adds selected product to `selectedProductIds` list.
    
-   Sends `selectedProducts` to insQuote component, which then adds these products to the Quote page.
    

[](https://help.salesforce.com/s?language=en_US)

## Services Called by this LWC

**insQuoteProductList** calls the following service:

-   [InsProductService:getEligibleProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__geteligibleproducts.htm&language=en_US&type=5 "Use this service to find and return a list of products that match the criteria you specify.")
    

[](https://help.salesforce.com/s?language=en_US)

## Other LWCs Used by this Component

**insQuoteProductList** uses these components:

[](https://help.salesforce.com/s?language=en_US)

-   **pubsub**
    
-   **input**
    

Did this article solve your issue?

Let us know so we can improve!

YesNo