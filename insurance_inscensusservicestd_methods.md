---
title: "InsCensusServiceStd Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd_methods.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd Methods

InsCensusServiceStd Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd Methods

These are the available InsCensusServiceStd methods.

-   **[InsCensusServiceStd:addMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addmembers.htm&language=en_US&type=5)**  
    Use this service to add group census members to a group census using an input JSON.
-   **[InsCensusServiceStd:addPlanSelections](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addplanselections.htm&language=en_US&type=5)**  
    Use this service to create `GroupCensusMemberPlan` records for existing `GroupCensusMember` records. It uses the `ContractGroupPlans` specified in the input JSON for adding plans to each `GroupCensusMember`. The service also accepts optional coverages per member such that primary members and dependents can be enrolled into different coverages under the same plan.
-   **[InsCensusServiceStd:createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createcontacts.htm&language=en_US&type=5)**  
    Use this service to create Contacts for census members.
-   **[InsCensusServiceStd:createUpdateAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createaccounts.htm&language=en_US&type=5)**  
    Use this service to create Person Accounts for the members in the given census. It also updates the existing person accounts using the `duplicateKeys` parameter.
-   **[InsCensusServiceStd:deleteAllMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestddeleteallmembers.htm&language=en_US&type=5)**  
    Use this service to delete all group census members of the group census passed as input into the service. This service supports small and medium groups with a maximum of 1,000 members (including primary members and dependents). The maximum number of records an org can have in the Group Census Member entity is 150,000.
-   **[InsCensusServiceStd:deleteMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletemembers.htm&language=en_US&type=5)**  
    Use this service to delete the group census members.
-   **[InsCensusServiceStd:deleteMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletememberswithplans.htm&language=en_US&type=5)**  
    Use this service to delete the group census members and the associated plans.
-   **[InsCensusServiceStd:findAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestdfindaccounts.htm&language=en_US&type=5)**  
    Search for existing person accounts by first name, last name, and email, or by a search key and group account.
-   **[InsCensusServiceStd:findContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestdfindcontacts.htm&language=en_US&type=5)**  
    Search for existing contacts by first name, last name, and email, or by a search key and group account.
-   **[InsCensusServiceStd:getFields](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getfields.htm&language=en_US&type=5)**  
    Use this service to retrieve field definitions and field API names for group census members and group census member plans.
-   **[InsCensusServiceStd:getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmembers.htm&language=en_US&type=5)**  
    Use this service to retrieve the members of a census from the `GroupCensusMember`. It also retrieves the headers based on the `fieldsetName`.
-   **[InsCensusServiceStd:getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmemberswithplans.htm&language=en_US&type=5)**  
    Use this service to retrieve the list of census members for a given `censusId`. Corresponding to these census members, the service retrieves the `ContractGroupPlanIds` from `GroupCensusMemberPlan`. The service also retrieves headers based on the `fieldsetName` and `planFieldsetName`.
-   **[InsCensusServiceStd:setCensusRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setcensusratingfacts.htm&language=en_US&type=5)**  
    Use this service to set `AttributeSelectedValues` on the `GroupCensus` record based on the rating fact passed to the service.
-   **[InsCensusServiceStd:setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5)**  
    Use this service to set `AttributeSelectedValues` on the `GroupCensusMember` records based on the rating fact passed to the service.
-   **[InsCensusServiceStd:updateMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatemembers.htm&language=en_US&type=5)**  
    Use this service to update the values of existing members in a census.
-   **[InsCensusServiceStd:updateMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatememberswithplans.htm&language=en_US&type=5)**  
    Use this service to populate a group census with primary members, their dependents, and their pre-enrolled plan. This service updates existing _`GroupCensusMember`_ by `memberKey` and creates _`GroupCensusMemberPlan`_ records for existing _`GroupCensusMember`_ records. It uses the _`ContractGroupPlans`_ specified in the input JSON to update plans for each _`GroupCensusMember`_.

Did this article solve your issue?

Let us know so we can improve!

YesNo