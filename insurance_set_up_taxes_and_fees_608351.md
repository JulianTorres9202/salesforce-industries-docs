---
title: "Set Up Taxes and Fees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_taxes_and_fees_608351.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Taxes and Fees

Set Up Taxes and Fees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Taxes and Fees

Set up taxes and fees directly on the Tax and Fee (price list) object, then attach them to root products and child specs. Or set up a new tax or fee from the Taxes and Fees tab on the root product or child spec page. Both methods save the data in the Tax and Fee object.

1.  From the App Launcher, open **Taxes and Fees.**
2.  On the Taxes and Fees list view, click **New**.
3.  Enter information into these fields:
    
    -   **Name**
        
    -   **Code**
        
    -   **Active**
        
        Leave this box selected unless you need to make this tax or fee inactive (unavailable to Vlocity services).
        
    -   **Amount**
        
        Enter an amount if this fee or tax will always be the same amount.
        
    -   **Effective From**
        
        Enter the date you want this tax or fee to go into effect. Vlocity Insurance use this date as the effective date for the tax or fee. Some services filter available taxes and fees based on this date.
        
    -   **Effective Until**
        
        The date when this tax or fee will expire and no longer be available to Vlocity Insurance services.
        
    -   **Currency Code**
        
        The currency code this tax or fee will be calculated in. Enter the three-letter code, not the symbol.
        
    -   **Parent Price List**
        
        Enter a value only if you've created a hierarchy of tax and fee prices in the Salesforce price list object.
        
    -   **Sequence**
        
    -   **Price Book**
        
        Enter a value only if you use the Price Book feature of Salesforce to create a hierarchy of taxes and fees.
        
    -   **Jurisdiction Id**
        
        Enter the jurisdiction Id for this tax or fee, such as a state, state-county, or state-city.
        
        Vlocity Insuranceservices query for jurisdiction Ids to narrow down taxes and fees that can apply to rated products.
        
    -   **Percent**
        
        Enter a value only if you're using percentage as the way this tax or fee is calculated.
        
    -   **Procedure Formula**
        
        Enter a formula to calculate the tax or fee amount.
        
    -   **Procedure Name**, **Procedure Source Mapping**
        
        For **Procedure Name**, enter the name of the calculation procedure or Integration Procedure you're using to calculate this tax or fee. For **Procedure Source Mapping**, enter the name of the output from this calculation procedure or Integration procedure.
        
        All of a product’s attributes are available to include in tax and fee calculations.
        
        If you’re using an Integration Procedure, you typically add a remote action that calls the service that calculates the tax or fee. Then you add the Integration Procedure to a product. After the product is added to a quote or policy, the user clicks **Rate Now**, and the Integration Procedure calculates the tax or fee.
        
        Leave these fields blank if you're using an Amount or Percent for this tax or fee.
        
    -   **Refundable**
        
        Select this option if this tax or fee can be refunded.
        
    -   **Type**
        
    -   **Rating Type**
        
    
4.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo