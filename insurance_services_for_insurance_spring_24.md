---
title: "Services for Insurance Spring '24"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_services_for_insurance_spring_24.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Services for Insurance Spring '24

Services for Insurance Spring '24[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Services for Insurance Spring '24

Explore new services and updates to existing services in Spring '24.

## New Services

-   [InsAsyncBulkService:getRequestStatusById](https://help.salesforce.com/s/articleView?id=ind.insurance_insasyncbulkservice_getrequeststatusbyid.htm&language=en_US&type=5 "Use this service to get the status of the async bulk request and its details associated with the request.")
    
    Use this service to get the status of the async bulk request and its details associated with the request.
    
-   [InsAsyncBulkService:getRequestStatusByUser](https://help.salesforce.com/s/articleView?id=ind.insurance_insasyncbulkservice_getrequeststatusbyuser.htm&language=en_US&type=5 "Use this service to get the status of async bulk requests and information about the associated async request items.")
    
    Use this service to get the status of async bulk requests and information about the associated async request items.
    
-   [InsEnrollmentServiceStd:enrollFamily](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd_enrollfamily.htm&language=en_US&type=5 "​Use this service to enroll one family within one root plan that includes a primary member and associated dependents with coverages.")
    
    ​Use this service to enroll one family within one root plan that includes a primary member and associated dependents with coverages.
    
-   [InsEnrollmentServiceStd:getRatedGroupProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd_getratedgroupproducts.htm&language=en_US&type=5 "Use this service to calculate price to opt for a root plan with coverages for a family. The service also provides employee and employer contributions for a policy before enrollment, and supports proration for new hires.")
    
    Use this service to calculate price to opt for a root plan with coverages for a family. The service also provides employee and employer contributions for a policy before enrollment, and supports proration for new hires.
    
-   [InsGroupClassService:getGroupClassesByContract](https://help.salesforce.com/s/articleView?id=ind.insurance_insgroupclassservice_getgroupclassesbycontract.htm&language=en_US&type=5 "​Use this service to get a list of eligible plans with the contractId that’s provided as input, and a list of eligible plans for the GroupclassId that’s provided as input.​")
    
    Use this service to get a list of eligible plans with the `contractId` that's provided as input, and a list of eligible plans for the GroupclassId that's provided as input.
    

## Updated Services

-   [InsCensusServiceStd:deleteAllMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestddeleteallmembers.htm&language=en_US&type=5 "Use this service to delete all group census members of the group census passed as input into the service. This service supports small and medium groups with a maximum of 1,000 members (including primary members and dependents). The maximum number of records an org can have in the Group Census Member entity is 150,000.")
    
    Use the new `batchSize` input option to set the size of the batch.
    
-   [InsCensusServiceStd:getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmembers.htm&language=en_US&type=5 "Use this service to retrieve the members of a census from the GroupCensusMember. It also retrieves the headers based on the fieldsetName.")
    
    Updated input options help retrieve a list of selected plans for each member.
    
-   [InsCensusServiceStd:getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmemberswithplans.htm&language=en_US&type=5 "Use this service to retrieve the list of census members for a given censusId. Corresponding to these census members, the service retrieves the ContractGroupPlanIds from GroupCensusMemberPlan. The service also retrieves headers based on the fieldsetName and planFieldsetName.")
    
    Use the `searchKey` input option to retrieve group census members and their families.
    
-   [InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.")
    
    Use the `createTransaction` and `includePaymentSchedule` options to create transaction and payment schedule entry details.
    
-   [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")
    
    Use the new `ratingDate` option to set the rating date used to price the input JSON.
    
-   [InsPolicyService:createRenewalPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalpolicy.htm&language=en_US&type=5 "Use this service to create a renewal policy from an existing policy.")
    
    Use the new `ratingDate` and `term` options to set the rating procedure for pricing the renewed policy and the policy term.
    
-   [InsPolicyService:getModifiedPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5 "Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.")
    
    Use the new `ratingDate` option to set the rating procedure for repricing the policy.
    
-   [InsPolicyService:prepareToRenewPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetorenewpolicy.htm&language=en_US&type=5 "Use this service to calculate the amount required for renewing an existing policy. This service returns renewal premium, taxes, and fees, or the renewal policy JSON without creating a policy.")
    
    Use the new `ratingDate` option to set the rating procedure for repricing the policy.
    
-   [InsPolicyService:removeInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5 "Use this service to remove an insured item from an existing policy.")
    
    Use the new `ratingDate` option to set the rating procedure for repricing the policy.
    
-   [InsProductAsyncRatingService:repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicerepriceproduct.htm&language=en_US&type=5 "Asynchronously recalculate the price of a product based on selectedProduct JSON and userInput.")
    
    Use the updated `effectiveDate` remote option to set the rating effective date using the YYYY-MM-DD HH:MM:SS" format.
    
-   [InsProductAsyncRatingService:startAsyncRating](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicestartasyncrating.htm&language=en_US&type=5 "Asynchronously calculate product prices based on a list of product IDs.")
    
    Use the updated `effectiveDate` remote option to set the rating effective date using the YYYY-MM-DD HH:MM:SS" format.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo