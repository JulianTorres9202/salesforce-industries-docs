---
title: "Services for Insurance Winter '23"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_services_for_insurance_winter_23.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Services for Insurance Winter '23

Services for Insurance Winter '23[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Services for Insurance Winter '23

Explore new services and updates to existing services for Insurance Winter '23 release.

## New Services

We added these new services in this release:

**InsClaimService**

-   [InsClaimService: createUpdateClaimRecoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__createupdateclaimrecoveries.htm&language=en_US&type=5 "Use this service to create or update records that represent a recovery of funds on an insurance claim.")
    
-   [InsClaimService: getClaimRecoveries](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__getclaimrecoveries.htm&language=en_US&type=5 "Use this service to get a list of claim recoveries for a claim.")
    

**InsCensusServiceStd**

-   [InsCensusServiceStd:addMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addmembers.htm&language=en_US&type=5 "Use this service to add group census members to a group census using an input JSON.")
    
-   [InsCensusServiceStd:addPlanSelections](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addplanselections.htm&language=en_US&type=5 "Use this service to create GroupCensusMemberPlan records for existing GroupCensusMember records. It uses the ContractGroupPlans specified in the input JSON for adding plans to each GroupCensusMember. The service also accepts optional coverages per member such that primary members and dependents can be enrolled into different coverages under the same plan.")
    
-   [InsCensusServiceStd:createUpdateAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createaccounts.htm&language=en_US&type=5 "Use this service to create Person Accounts for the members in the given census. It also updates the existing person accounts using the duplicateKeys parameter.")
    
-   [InsCensusServiceStd:createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createcontacts.htm&language=en_US&type=5 "Use this service to create Contacts for census members.")
    
-   [InsCensusServiceStd:deleteMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletemembers.htm&language=en_US&type=5 "Use this service to delete the group census members.")
    
-   [InsCensusServiceStd:deleteMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletememberswithplans.htm&language=en_US&type=5 "Use this service to delete the group census members and the associated plans.")
    
-   [InsCensusServiceStd:getFields](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getfields.htm&language=en_US&type=5 "Use this service to retrieve field definitions and field API names for group census members and group census member plans.")
    
-   [InsCensusServiceStd:getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmembers.htm&language=en_US&type=5 "Use this service to retrieve the members of a census from the GroupCensusMember. It also retrieves the headers based on the fieldsetName.")
    
-   [InsCensusServiceStd:getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmemberswithplans.htm&language=en_US&type=5 "Use this service to retrieve the list of census members for a given censusId. Corresponding to these census members, the service retrieves the ContractGroupPlanIds from GroupCensusMemberPlan. The service also retrieves headers based on the fieldsetName and planFieldsetName.")
    
-   [InsCensusServiceStd:setCensusRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setcensusratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensus record based on the rating fact passed to the service.")
    
-   [InsCensusServiceStd:setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5 "Use this service to set AttributeSelectedValues on the GroupCensusMember records based on the rating fact passed to the service.")
    
-   [InsCensusServiceStd:updateMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatemembers.htm&language=en_US&type=5 "Use this service to update the values of existing members in a census.")
    
-   [InsCensusServiceStd:updateMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatememberswithplans.htm&language=en_US&type=5 "Use this service to populate a group census with primary members, their dependents, and their pre-enrolled plan. This service updates existing GroupCensusMember by memberKey and creates GroupCensusMemberPlan records for existing GroupCensusMember records. It uses the ContractGroupPlans specified in the input JSON to update plans for each GroupCensusMember.")
    

**InsContractServiceStd**

-   [InsContractServiceStd:createUpdateContract](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservicestd__createupdatecontract.htm&language=en_US&type=5 "Use this service to create or update a contract for the given quote. ​")
    

**InsEnrollmentServiceStd**

-   [InsEnrollmentServiceStd:enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollmembers.htm&language=en_US&type=5 "Use this service to enroll census members into their selected plans.")
    
-   [InsEnrollmentServiceStd:enrollPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollplans.htm&language=en_US&type=5 "Use this service to create insurance policy (InsurancePolicy) records for member's selected medical, dental, vision, and other plans.")
    
-   [InsEnrollmentServiceStd:getMemberEnrollments](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicegetmemberenrollmentsstd_632876.htm&language=en_US&type=5 "Use this service to retrieve current enrollments for a member. This service takes one or more census member Ids and returns enrolled plans for the member and associated dependents.")
    

**InsPolicyService**

-   [InsPolicyService:createReinstatementPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_createreinstatementpolicy.htm&language=en_US&type=5 "Use this service to reinstate a canceled policy.")
    

## Updated Services

We updated these services in this release:

**InsPolicyService**

-   [InsPolicyService:cancelPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__cancelpolicy.htm&language=en_US&type=5 "Use this service to cancel an existing insurance policy.")
    
-   [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")
    
-   [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")
    

**InsProductService**

-   [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo