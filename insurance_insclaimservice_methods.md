---
title: "InsClaimService Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice_methods.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimService Methods

InsClaimService Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimService Methods

Create and update claims, verify coverages, recover funds on claims, and run underwriting and state transition rules with the help of the claim service methods.

-   **[InsClaimService:createUpdateClaim](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservicecreateupdateclaim_630113.htm&language=en_US&type=5)**  
    Use this service to create or update a claim.
-   **[InsClaimService:createUpdateClaimRecoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__createupdateclaimrecoveries.htm&language=en_US&type=5)**  
    Use this service to create or update records that represent a recovery of funds on an insurance claim.
-   **[InsClaimService:getClaimRecoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__getclaimrecoveries.htm&language=en_US&type=5)**  
    Use this service to get a list of claim recoveries for a claim.
-   **[InsClaimService:getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__getrulelogs.htm&language=en_US&type=5)**  
    Use this service to retrieve rule logs for a claim, sorted by execution date in ascending order.
-   **[InsClaimService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokeproductrules.htm&language=en_US&type=5)**  
    Use this service in claim flows to invoke underwriting rules you've added to a product.
-   **[InsClaimService:invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokerules.htm&language=en_US&type=5)**  
    Use this service to invoke state transition rules associated with a target state transition on a target claim. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target claim to the new state.
-   **[InsClaimService:verifyCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__verifycoverage.htm&language=en_US&type=5)**  
    Use this service to verify valid insurance coverage for a policyholder who is filing a claim.

Did this article solve your issue?

Let us know so we can improve!

YesNo