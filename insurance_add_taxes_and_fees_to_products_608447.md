---
title: "Add Taxes and Fees to Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_taxes_and_fees_to_products_608447.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Taxes and Fees to Products

Add Taxes and Fees to Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Taxes and Fees to Products

Add existing taxes and fees to root products, insured item specs, insured party specs, and coverage specs.

[](https://help.salesforce.com/s?language=en_US)You can also create new taxes and fees on specific products and child specs.

[](https://help.salesforce.com/s?language=en_US)Note

We recommend that you not attach a tax or fee to a coverage, insured item, or insured party (product child item) if the tax or fee is calculated by a Calculation Procedure or an Integration Procedure.

For product child items that are part of insurance products that can create multi-instance quotes and policies, a tax or fee that uses a Calculation Procedure or Integration Procedure can instantiate many times. This can cause Vlocity to hit its SQL limit.

You can attach taxes or fees to a product child item that won't be attached to any root product intended for multi-instance use.

1.  Add an existing tax or fee to a product:
    1.  On the Product Detail page, click the Taxes and Fees tab.
    2.  On the right side of the tab, click **Add**.
    3.  On the Add Taxes and Fees window, choose the tax(es) or fee(s) you want to add by checking the box on the left.
    4.  Click **Select**.
2.  Or, add a new tax and fee to a product:
    1.  On the Product Detail page, click the Taxes and Fees tab.
    2.  On the right side of the tab, click **Add**.
    3.  On the Add Taxes and Fees window, click Create Tax and Fee Record.
    4.  Fill out the New Tax and Fee
    5.  Click **Select**.

Did this article solve your issue?

Let us know so we can improve!

YesNo