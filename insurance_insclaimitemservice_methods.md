---
title: "InsClaimItemService Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice_methods.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService Methods

InsClaimItemService Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService Methods

Manage claim line items, calculate coverages, process and cancel payments, and gather information about parties on a claim with the help of the claim item service methods. If you use a payment authorization workflow, use a service method to verify a team member's authority to pay or approve a financial amount.

-   **[InsClaimItemService:add](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__add.htm&language=en_US&type=5)**  
    Use this service to add a claim line item to a specified claim item object.
-   **[InsClaimItemService:calculateCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__calculatecoverages.htm&language=en_US&type=5)**  
    Use this service to calculate the coverage amount and adjusted amount for a claim line item. These amounts are used as payment amount when the claims adjuster pays the claim line item.
-   **[InsClaimItemService:cancelPayments](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__cancelpayments.htm&language=en_US&type=5)**  
    Use this service to cancel claim loss and expense payments.
-   **[InsClaimItemService:claimCoverageValuation](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice_claimcoveragevaluation.htm&language=en_US&type=5)**  
    Use this service to verify that users have the authority to pay or approve amounts in different types of financial activities.
-   **[InsClaimItemService:createPayments](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__createpayments.htm&language=en_US&type=5)**  
    Use this service to create and save claim payment records based on the line item IDs and the `groupPayments` option.
-   **[InsClaimItemService:delete](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__delete.htm&language=en_US&type=5)**  
    Use this service to delete a claim line item from a claim object.
-   **[InsClaimItemService:getClaimItems](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimitems.htm&language=en_US&type=5)**  
    Use this service to retrieve the list of Claimants and their corresponding open ClaimCoverages with the respective line items (loss or expense).
-   **[InsClaimItemService: getClaimLineItemFields](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimlineitemfields.htm&language=en_US&type=5)**  
    Use this service to retrieve the list of fields of a field set (and optionally the field's values). This field set is specific for a particular CoverageSpec.
-   **[InsClaimItemService:getCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getcoverages.htm&language=en_US&type=5)**  
    Use this service to get coverages that apply to a specific claim.
-   **[InsClaimItemService:getInsuranceCodes](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getinsurancecodes.htm&language=en_US&type=5)**  
    Use this service to get a list of insurance codes that correspond to the coverages associated with claims.
-   **[InsClaimItemService:getInvolvedItems](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getinvolveditems.htm&language=en_US&type=5)**  
    Use this service to get a list of involved items (property) and/or involved people (parties) for a specific claim.
-   **[InsClaimItemService:getPartyContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getpartycontacts.htm&language=en_US&type=5)**  
    Use this service to get a list of all the contact information for all involved parties in a specified claim.
-   **[InsClaimItemService:getPayees](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getpayees.htm&language=en_US&type=5)**  
    Use this service to return a list of payees for a specified claim.
-   **[InsClaimItemService:invokeInitiatePaymentIP](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__invokeinitiatepaymentip.htm&language=en_US&type=5)**  
    Use this service to initiate loss or expense payments.
-   **[InsClaimItemService:saveInvolvedItem](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__saveinvolveditem.htm&language=en_US&type=5)**  
    Use this service to update the total reserve amount of an involved property or involved injury record.
-   **[InsClaimItemService:update](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__update.htm&language=en_US&type=5)**  
    Use this service to update a claim line item to a specified claim item object.

Did this article solve your issue?

Let us know so we can improve!

YesNo