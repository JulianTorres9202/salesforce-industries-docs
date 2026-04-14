---
title: "Harmonized LWCs and Services"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_harmonized_lwcs_and_services_603569.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Harmonized LWCs and Services

Harmonized LWCs and Services[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Harmonized LWCs and Services

You don't have to do anything special to make harmonized LWCs and services work with your harmonized data. They work as well with the Salesforce object model as they do with the Vlocity managed package object model.

[](https://help.salesforce.com/s?language=en_US)

## Record Pages that Work with the Harmonized Insurance Object Model

On these LWC-based UIs, you can do the following tasks on the harmonized Insurance object model:

-   [Quote Record Page](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_ui_lwc_catalog_611486.htm&language=en_US&type=5 "The Quote UI is made up of a bunch of Lightning web components (LWCs) to get you started with providing your agents with functionality they can use to create quotes, issue policies, and manage policies.")
    
    -   Issue a new business or endorsement quote to create policy and policy versions.
        
    -   Modify coverages/insured items, and Reprice.
        
    -   Execute products and state transition rules.
        
-   Policy Record Page
    
    -   Modify an existing policy to create an endorsement quote.
        
-   [](https://help.salesforce.com/s?language=en_US)
    
    [Claims Record Page](https://help.salesforce.com/s/articleView?id=ind.insurance_claims_617267.htm&language=en_US&type=5 "Set up claim products and create dynamic first notice of loss intake flows for your users. Give claims adjusters a cohesive view of claims and financial data so they can efficiently assess and adjudicate claims. Establish financial controls and automatically route requests for financial approval to the appropriate supervisors and managers.")
    
    -   Vlocity Claim Participants
        
        -   View participants and their involvements.
            
        -   Add participants.
            
    -   Vlocity Claim Items Chart
        
        -   Displays the financial summary of the claim.
            
    -   Vlocity Claim Items
        
        -   Open coverages.
            
        -   Manage expense and loss reserves.
            
        -   Manage expense and loss payments.
            
    -   Vlocity Policy Terms Standings
        
        -   View current standing of policy terms.
            

[](https://help.salesforce.com/s?language=en_US)

## LWCs Harmonized to Work With FSC Insurance Policy

We've harmonized the following LWCs:

-   insPolicy
    
-   insProductInstance
    
-   insProductMatrix
    
-   inPolicyManagement
    
-   insOsSingleInstance
    
-   insOsMultiInstanceGrandchildren
    
-   insVersionHistory
    

[](https://help.salesforce.com/s?language=en_US)

## Vlocity Insurance Services Harmonized to Work With FSC Insurance Policy

We've harmonized the following InsPolicyService services:

-   [InsPolicyService:calculateTaxesAndFees](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__calculatetaxesandfees.htm&language=en_US&type=5 "Use this service to calculate and save taxes and fees on a target asset (policy).")
    
-   [InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")
    
-   [InsPolicyService:createPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpaymentschedule.htm&language=en_US&type=5 "The InsPolicyService:createPaymentSchedule service creates a payment schedule (and optionally an initial payment transaction) for the target policy. This applies to Insurance Policy object only. The Policy (Asset) object is not supported.")
    
-   [InsPolicyService:createPolicyTerms](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyterms.htm&language=en_US&type=5 "Create policy terms in the AssetTerm__c or InsurancePolicyTerm__c (for Salesforce FSC) object for all the power attributes at the Policy and PolicyCoverage level. A power attribute is an attribute that has an attribute class, attribute scope, applicable item, and applicable actions.")
    
-   [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")
    
-   [InsPolicyService:createTransaction](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createtransaction.htm&language=en_US&type=5 "Use this service to create a transaction on a target policy.")
    
-   [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")
    
-   [InsPolicyService:getInsuredItems](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getinsureditems.htm&language=en_US&type=5 "Use this service to find and return insured items and insured parties from a policy (asset).")
    
-   [InsPolicyService:getModifiedPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5 "Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.")
    
-   [InsPolicyService:getPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpaymentschedule.htm&language=en_US&type=5 "The InsPolicyService:getPaymentSchedule service returns the payment schedule of the InsurancePolicy. The Policy (Asset) object is not supported.")
    
-   [InsPolicyService:getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicydetails.htm&language=en_US&type=5 "Use this service to get the coverages, insured items, pricing, and other information for an existing insurance policy, including optional coverages that weren't selected.")
    
-   [InsPolicyService:getPolicyVersions](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpolicyversions.htm&language=en_US&type=5 "Use this service to retrieve the different versions of a policy. The service returns a list of policies with high level fields determined by the Policy field set PolicyCompareHeader.")
    
-   [InsPolicyService:getRuleLogs](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getrulelogs.htm&language=en_US&type=5 "This service retrieves rule logs for a target policy, sorted by execution date in ascending order.")
    
-   [InsPolicyService:initiateLapseGracePeriod](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__initiatelapsegraceperiod.htm&language=en_US&type=5 "This service initiates a grace period on a policy, lapses a policy, or does nothing to a policy, depending on factors of the policy.")
    
-   [InsPolicyService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__invokeproductrules.htm&language=en_US&type=5 "Use this service with a policy to invoke underwriting rules you've added to a product.")
    
-   [InsPolicyService:invokeRules](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__invokerules.htm&language=en_US&type=5 "Use this service to invoke state transition rules associated with a target state transaction on a target policy. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target policy to the new state.")
    
-   [InsPolicyService:modifyPaymentSchedule](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__modifypaymentschedule.htm&language=en_US&type=5 "Use this service to modify an existing payment schedule based on a new Premium Frequency.")
    
-   [InsPolicyService:prepareToCancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetocancelpolicy.htm&language=en_US&type=5 "Use this service to calculate the premium price difference before canceling a policy. The service prorates the premium, fee, and tax amounts, and calculates the premium, fee, and tax refund.")
    
-   [InsPolicyService:removeInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5 "Use this service to remove an insured item from an existing policy.")
    
-   [InsPolicyService:verifyCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__verifycoverage.htm&language=en_US&type=5 "Use this service to verify valid insurance coverage for a policyholder who is filing a claim.")
    

We've harmonized the following InsEnrollmentService services:

-   [InsEnrollmentService:enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__enrollmembers.htm&language=en_US&type=5 "Use this service to enroll census members into their selected plans.")
    
-   [InsEnrollmentService:enrollPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__enrollplans.htm&language=en_US&type=5 "Use this service to create policy (Asset or Insurance Policy) records for enrollee selected medical, dental, vision, and other plans.")
    
-   [InsEnrollmentService:getMemberEnrollments](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicegetmemberenrollments_632876.htm&language=en_US&type=5 "Use this service to retrieve current enrollments for a member so they can edit the benefits. This service also takes one or more census member Ids and returns enrolled plans for the member and their dependents.")
    
-   [InsEnrollmentService:modifyEnrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__modifyenrollment.htm&language=en_US&type=5 "Use this service to modify the enrollments, dependents, and coverages of each enrollment for input members. You can use this service to add new or remove existing plans or add or remove dependents.")
    

[](https://help.salesforce.com/s?language=en_US)

## Vlocity Insurance Services Harmonized to Work With FSC Insurance Claim

We've harmonized the following services for InsClaimService class:

[](https://help.salesforce.com/s?language=en_US)

-   [InsClaimService:createUpdateClaim](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservicecreateupdateclaim_630113.htm&language=en_US&type=5 "Use this service to create or update a claim.")
    
-   [InsClaimService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokeproductrules.htm&language=en_US&type=5 "Use this service in claim flows to invoke underwriting rules you've added to a product.")
    
-   [InsClaimService:verifyCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__verifycoverage.htm&language=en_US&type=5 "Use this service to verify valid insurance coverage for a policyholder who is filing a claim.")
    

We've harmonized the following services for InsClaimItemService class:

[](https://help.salesforce.com/s?language=en_US)

-   [InsClaimItemService:add](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__add.htm&language=en_US&type=5 "Use this service to add a claim line item to a specified claim item object.")
    
-   [InsClaimItemService:calculateCoverages](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__calculatecoverages.htm&language=en_US&type=5 "Use this service to calculate the coverage amount and adjusted amount for a claim line item. These amounts are used as payment amount when the claims adjuster pays the claim line item.")
    
-   [InsClaimItemService:createPayments](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__createpayments.htm&language=en_US&type=5 "Use this service to create and save claim payment records based on the line item IDs and the groupPayments option.")
    
-   [InsClaimItemService:invokeInitiatePaymentIP](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__invokeinitiatepaymentip.htm&language=en_US&type=5 "Use this service to initiate loss or expense payments.")
    
-   [InsClaimItemService:delete](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__delete.htm&language=en_US&type=5 "Use this service to delete a claim line item from a claim object.")
    
-   [InsClaimItemService:getClaimItems](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimitems.htm&language=en_US&type=5 "Use this service to retrieve the list of Claimants and their corresponding open ClaimCoverages with the respective line items (loss or expense).")
    
-   [InsClaimItemService: getClaimLineItemFields](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimlineitemfields.htm&language=en_US&type=5 "Use this service to retrieve the list of fields of a field set (and optionally the field's values). This field set is specific for a particular CoverageSpec.")
    
-   [InsClaimItemService:update](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__update.htm&language=en_US&type=5 "Use this service to update a claim line item to a specified claim item object.")
    

We've harmonized the following services for InsClaimCoverageService class:

[](https://help.salesforce.com/s?language=en_US)

-   [InsClaimCoverageService:createUpdateCoverage](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimcoverageservice_createupdatecoverage.htm&language=en_US&type=5 "Use this service to create a claim coverage or update an existing claim coverage.")
    
-   [InsClaimCoverageService:invokeProductRules](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimcoverageservice__invokeproductrules.htm&language=en_US&type=5 "Use this service when creating claim coverages to invoke product rules for state transitions.")
    

We've harmonized the following services for InsPolicyTermsService class:

[](https://help.salesforce.com/s?language=en_US)

-   [InsPolicyTermsService: process](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice__process.htm&language=en_US&type=5 "This service retrieves policy terms and calls the policy term's corresponding Attribute Class to process details. For the custom classes, the default method name for the attribute class is - process<Attribute>.")
    
-   [InsPolicyTermsService:getCurrentStanding](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservicegetcurrentstanding_638455.htm&language=en_US&type=5 "Use this service to get a list of amounts that represent the current standing of the policy terms associated with a policy or a claim.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo