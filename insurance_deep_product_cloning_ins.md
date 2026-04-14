---
title: "Deep Product Cloning for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_deep_product_cloning_ins.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Deep Product Cloning for Insurance

Deep Product Cloning for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Deep Product Cloning for Insurance

You can configure Insurance to deep clone an insurance policy product. A deep clone includes the coverage specs, insured item specs, rating facts, rules, attributes, and pricebook entries of the policy product.

[](https://help.salesforce.com/s?language=en_US)Insurance uses a custom Visualforce page to deep clone policy products.

You can either configure Insurance to override the existing Clone button on the Product page, or you can leave the Clone button as is and create a custom button for deep cloning on the Product page.

## Override the Existing Clone Button

To configure Insurance to override the existing Clone button on the Product page, follow these steps.

1.  From Setup, in Object Manager, find and select **Product**.
    
2.  Click **Buttons, Links, and Actions**.
    
3.  From the Action menu for Clone, select **Edit**.
    
4.  Select **Visualforce Page**, then specify **InsuranceProductCloner**.
    
5.  Click **Save**.
    

## Create a Custom Deep Clone Button

To leave the Clone button as is and create a custom button for deep cloning on the Product page, follow these steps.

1.  From Setup, in Object Manager, find and select **Product**.
    
2.  Click **Buttons, Links, and Actions**.
    
3.  In **Content Source**, select **Visualforce Page**.
    
4.  In the **Content** field, select **InsuranceProductCloner**.
    
5.  Specify a **Label** and a **Name**.
    
6.  Click **Save**.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo