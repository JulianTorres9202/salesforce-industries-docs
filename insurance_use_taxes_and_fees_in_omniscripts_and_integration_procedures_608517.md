---
title: "Use Taxes and Fees in OmniScripts and Integration Procedures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_use_taxes_and_fees_in_omniscripts_and_integration_procedures_608517.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Use Taxes and Fees in OmniScripts and Integration Procedures

Use Taxes and Fees in OmniScripts and Integration Procedures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Use Taxes and Fees in OmniScripts and Integration Procedures

You can create specific OmniScripts and Integration Procedures to calculate taxes, fees, or both--separate from quoting or policy flows. You can also add tax and fee calculations to quote and policy flows.

[](https://help.salesforce.com/s?language=en_US)To add tax and fee calculations to OmniScripts and Integration Procedures, you must create the tax and fee records, including the formula that our services will use to calculate the tax or fee.

[](https://help.salesforce.com/s?language=en_US)Then you can add services to your OmniScripts and Integration Procedures that will retrieve the tax or fee record and use the formula to calculate the tax or fee on a quote or policy.

[](https://help.salesforce.com/s?language=en_US)Vlocity Insurance services also account for the need to prorate taxes and fees, and to calculate refunds for taxes and fees when a policy is adjusted or canceled.

[](https://help.salesforce.com/s?language=en_US)

## Services That Calculate Taxes and Fees

These services just calculate taxes and fees:

-   [InsQuoteService:calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__calculatetaxesandfees.htm&language=en_US&type=5 "Use this service to calculate and save taxes and fees on a target quote.")
    
-   [InsPolicyService:calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__calculatetaxesandfees.htm&language=en_US&type=5 "Use this service to calculate and save taxes and fees on a target asset (policy).")
    

These services can calculate taxes and fees, or retrieve values for taxes and fees as part of what they do:

-   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    
-   [InsProductService:repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.")
    
-   [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")
    
-   [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")
    
-   [InsPolicyService:getModifiedPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5 "Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.")
    
-   [InsPolicyService:removeInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5 "Use this service to remove an insured item from an existing policy.")
    
-   [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")
    
-   [InsPolicyService:prepareToCancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetocancelpolicy.htm&language=en_US&type=5 "Use this service to calculate the premium price difference before canceling a policy. The service prorates the premium, fee, and tax amounts, and calculates the premium, fee, and tax refund.")
    
-   [InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")
    
-   [InsPolicyService:getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5 "Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.")
    
-   [InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo