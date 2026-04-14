---
title: "Services for Insurance Summer '21"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_services_for_insurance_summer__21.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Services for Insurance Summer '21

Services for Insurance Summer '21[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Services for Insurance Summer '21

We've added new services and updated existing services for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Services

We've added the following new services in this release:

**InsClaimItemService**

-   [InsClaimItemService:createPayments](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__createpayments.htm&language=en_US&type=5 "Use this service to create and save claim payment records based on the line item IDs and the groupPayments option.")
    
-   [InsClaimItemService:invokeInitiatePaymentIP](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__invokeinitiatepaymentip.htm&language=en_US&type=5 "Use this service to initiate loss or expense payments.")
    

[](https://help.salesforce.com/s?language=en_US)**InsCommissionService**

-   [InsCommissionService:adjust](https://help.salesforce.com/s/articleView?id=ind.insurance_inscommissionservice__adjust.htm&language=en_US&type=5 "Use this service to adjust a Producer Commission amount.")
    
-   [InsCommissionService:calculate](https://help.salesforce.com/s/articleView?id=ind.insurance_inscommissionservice__calculate.htm&language=en_US&type=5 "Use this service to calculate the commission for a producer.")
    

**InsQuoteService**

-   [InsQuoteService:getAccountQuotes](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getaccountquotes.htm&language=en_US&type=5 "Use this service to retrieve quote records associated with an accountId.")
    

[](https://help.salesforce.com/s?language=en_US)

## Updated Services

We've updated the following services in this release:

**InsClaimService**

-   [InsClaimService: createUpdateClaim](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservicecreateupdateclaim_630113.htm&language=en_US&type=5 "Use this service to create or update a claim.")
    

**InsClaimItemService**

-   [InsClaimItemService:add](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__add.htm&language=en_US&type=5 "Use this service to add a claim line item to a specified claim item object.")
    
-   [InsClaimItemService:calculateCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__calculatecoverages.htm&language=en_US&type=5 "Use this service to calculate the coverage amount and adjusted amount for a claim line item. These amounts are used as payment amount when the claims adjuster pays the claim line item.")
    
-   [InsClaimItemService:update](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__update.htm&language=en_US&type=5 "Use this service to update a claim line item to a specified claim item object.")
    

**InsPolicyService**

-   [InsPolicyService:createPolicyTerms](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyterms.htm&language=en_US&type=5 "Create policy terms in the AssetTerm__c or InsurancePolicyTerm__c (for Salesforce FSC) object for all the power attributes at the Policy and PolicyCoverage level. A power attribute is an attribute that has an attribute class, attribute scope, applicable item, and applicable actions.")
    
-   [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")
    
-   [InsPolicyService:createTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createtransaction.htm&language=en_US&type=5 "Use this service to create a transaction on a target policy.")
    
-   [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")
    

**InsPolicyTermsService**

-   [InsPolicyTermsService: getCurrentStanding](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservicegetcurrentstanding_638455.htm&language=en_US&type=5 "Use this service to get a list of amounts that represent the current standing of the policy terms associated with a policy or a claim.")
    
-   [InsPolicyTermsService: process](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice__process.htm&language=en_US&type=5 "This service retrieves policy terms and calls the policy term's corresponding Attribute Class to process details. For the custom classes, the default method name for the attribute class is - process<Attribute>.")
    

[](https://help.salesforce.com/s?language=en_US)**InsurancePolicyTransactionService**

-   [InsurancePolicyTransactionService:reverseTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_insurancepolicytransactionservice_reversetransaction.htm&language=en_US&type=5 "Use this service to reverse an insurance policy transaction.")
    

[](https://help.salesforce.com/s?language=en_US)**InsQuoteService**

-   [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")
    
-   [InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
    
-   [InsQuoteService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in quote flows to invoke underwriting rules you've added to a product.")
    
-   [InsQuoteService:invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokerules.htm&language=en_US&type=5 "Use this service to Invoke state transition rules associated with a target state transition on a target quote.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo