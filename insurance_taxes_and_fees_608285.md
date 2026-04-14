---
title: "Taxes and Fees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_taxes_and_fees_608285.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Taxes and Fees

Taxes and Fees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Taxes and Fees

Calculate applicable taxes on Vlocity Insurance quotes and policies, and applicable fees on Vlocity Health and Vlocity Insurance quotes and policies.

Vlocity taxes and fees use the Salesforce price list object, which we've renamed Tax and Fee. You'll create all your taxes and fees on the Tax and Fee (price list) object, then attach them to products. Vlocity Insurance services use the data in the Tax and Fee object to calculate applicable taxes and fees, and save that data to a quote or policy.

[](https://help.salesforce.com/s?language=en_US)

## Taxes and Fees in Context

You can apply taxes and fees to the premiums to:

-   Policies
    
-   Coverages
    
-   Insured Items
    
-   Insured Parties
    

To apply taxes and fees to these premiums, you attach them to root products and/or child specs. Vlocity services take the information from the specs and calculate the taxes and fees.

Vlocity services calculate taxes and fees on quotes and when premium-bearing endorsements happen. This can include calculating refunds for refundable taxes and fees when a policy is canceled or changed in a way that decreases premiums.

Taxes and fees can use one of four types of calculation:

-   Amount
    
-   Percentage
    
-   Calculation Procedure
    
-   Integration Procedure
    

If you use an external system to calculate taxes and/or fees, you can use an Integration Procedure to so Vlocity services can call the external system when Vlocity needs a tax or fee calculated.

To start using Taxes and Fees:

-   [Set Up Taxes and Fees](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_taxes_and_fees_608351.htm&language=en_US&type=5 "Set up taxes and fees directly on the Tax and Fee (price list) object, then attach them to root products and child specs. Or set up a new tax or fee from the Taxes and Fees tab on the root product or child spec page. Both methods save the data in the Tax and Fee object.")
    
    [](https://help.salesforce.com/s?language=en_US)Set up taxes and fees directly on the Tax and Fee (price list) object, then attach them to root products and child specs. Or set up a new tax or fee from the Taxes and Fees tab on the root product or child spec page. Both methods save the data in the Tax and Fee object.
    
-   [Add Taxes and Fees to Products](https://help.salesforce.com/s/articleView?id=ind.insurance_add_taxes_and_fees_to_products_608447.htm&language=en_US&type=5 "Add existing taxes and fees to root products, insured item specs, insured party specs, and coverage specs.")
    
    [](https://help.salesforce.com/s?language=en_US)Create new or add existing taxes and fees to root products, insured item specs, insured party specs, and coverage specs.
    
-   [Add Conditions to Taxes and Fees](https://help.salesforce.com/s/articleView?id=ind.insurance_add_conditions_to_taxes_and_fees_608497.htm&language=en_US&type=5 "Some taxes and fees may only be applicable to a quote or policy under certain conditions. To make this work, you can add conditions to taxes and fees after you've applied them to root products and child specs.")
    
    [](https://help.salesforce.com/s?language=en_US)Some taxes and fees may only be applicable to a quote or policy under certain conditions. To make this work, you can add conditions to taxes and fees after you've applied them to root products and child specs.
    
-   Setting Attributes to be Rated for Taxes and Fees
    
    [](https://help.salesforce.com/s?language=en_US)In addition to setting up the taxes and fees, and attaching them to root products and child spec, you need to set the Tax and Fee Rating Attribute on any attributes that you need to contribute to the rating of any tax or fee.
    
    [](https://help.salesforce.com/s?language=en_US)To learn more, see [Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.") and [Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5 "Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.").
    
-   [Use Taxes and Fees in OmniScripts and Integration Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_use_taxes_and_fees_in_omniscripts_and_integration_procedures_608517.htm&language=en_US&type=5 "You can create specific OmniScripts and Integration Procedures to calculate taxes, fees, or both--separate from quoting or policy flows. You can also add tax and fee calculations to quote and policy flows.")
    
    [](https://help.salesforce.com/s?language=en_US)Create specific OmniScripts and Integration Procedures to calculate taxes, fees, or both--separate from quoting or policy flows. You can also add tax and fee calculations to quote and policy flows.
    

-   **[Set Up Taxes and Fees](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_taxes_and_fees_608351.htm&language=en_US&type=5)**  
    Set up taxes and fees directly on the Tax and Fee (price list) object, then attach them to root products and child specs. Or set up a new tax or fee from the Taxes and Fees tab on the root product or child spec page. Both methods save the data in the Tax and Fee object.
-   **[Add Taxes and Fees to Products](https://help.salesforce.com/s/articleView?id=ind.insurance_add_taxes_and_fees_to_products_608447.htm&language=en_US&type=5)**  
    Add existing taxes and fees to root products, insured item specs, insured party specs, and coverage specs.
-   **[Add Conditions to Taxes and Fees](https://help.salesforce.com/s/articleView?id=ind.insurance_add_conditions_to_taxes_and_fees_608497.htm&language=en_US&type=5)**  
    Some taxes and fees may only be applicable to a quote or policy under certain conditions. To make this work, you can add conditions to taxes and fees after you've applied them to root products and child specs.
-   **[Use Taxes and Fees in OmniScripts and Integration Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_use_taxes_and_fees_in_omniscripts_and_integration_procedures_608517.htm&language=en_US&type=5)**  
    You can create specific OmniScripts and Integration Procedures to calculate taxes, fees, or both--separate from quoting or policy flows. You can also add tax and fee calculations to quote and policy flows.

Did this article solve your issue?

Let us know so we can improve!

YesNo