---
title: "InsCensusService Methods"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice_methods.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService Methods

InsCensusService Methods[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService Methods

These are the available InsCensusService methods.

-   **[InsCensusService:addMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__addmembers.htm&language=en_US&type=5)**  
    Use this service to add members to a census via an input JSON. Guest user access is enabled for this service.
-   **[InsCensusService:addPlanSelections](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__addplanselections.htm&language=en_US&type=5)**  
    Use this service to insert pre-enrolled plans for each member specified in the input.
-   **[InsCensusService:cloneCensus](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__clonecensus.htm&language=en_US&type=5)**  
    Use this service to clone a census and all the census members.
-   **[InsCensusService:createAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createaccounts.htm&language=en_US&type=5)**  
    Use this service to create Person Accounts for the members in the given census.
-   **[InsCensusService:convertLeadAndCreateCensus](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__convertleadandcreatecensus.htm&language=en_US&type=5)**  
    Use this service to extend the Lead Conversion Salesforce feature, allowing users to include Lead census information and map this data to the Vlocity Group Account Census objects while converting the Lead.
-   **[InsCensusService:createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createcontacts.htm&language=en_US&type=5)**  
    Use this service to create Contacts for census members and community (portal) users.
-   **[InsCensusService:deleteMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__deletemembers.htm&language=en_US&type=5)**  
    Use this service to delete the members from a census.
-   **[InsCensusService:getFields](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getfields.htm&language=en_US&type=5)**  
    Use this service to retrieve field definitions and field API names for group census members and group census plans. Guest user access is enabled for this service.
-   **[InsCensusService:getMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmemberratingfacts.htm&language=en_US&type=5)**  
    Use this service to retrieve rating fact data for census members, for use as user Inputs for the `InsProductService:getRatedProducts` service.
-   **[InsCensusService:getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmembers.htm&language=en_US&type=5)**  
    Use this service to retrieve the members of a census. It also retrieves the fields. Guest user access is enabled for this service.
-   **[InsCensusService:getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmemberswithplans.htm&language=en_US&type=5)**  
    Use this service to retrieve members of a census and their pre-enrolled plans. This service also retrieves field definitions for the `GroupCensusMember__c` and `GroupCensusMemberPlan__c` fields.
-   **[InsCensusService:getQualifiedCensusMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getqualifiedcensusmembers.htm&language=en_US&type=5)**  
    Use this service to retrieve members that qualify for rating per family. Filters out dependents based on age, region, number of dependents.
-   **[InsCensusService:sendMassEmail](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__sendmassemail.htm&language=en_US&type=5)**  
    Use this service to send emails to all members of a census. For example, you can use this service to send an invitation to enroll in a health insurance plan to all members of a customer's census.
-   **[InsCensusService:setCensusRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__setcensusratingfacts.htm&language=en_US&type=5)**  
    Use this service to associate a Rating Fact spec to a census, and automatically extract information from the census fields to populate the Attribute Selected Values for the census, based on the Rating Fact.
-   **[InsCensusService:setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__setmemberratingfacts.htm&language=en_US&type=5)**  
    Use this service to associate a Rating Facts Spec to a census member, and automatically extract information from the census member fields to populate the Attribute Selected Values for the member, based on the Rating Fact.
-   **[InsCensusService:updateMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__updatemembers.htm&language=en_US&type=5)**  
    Use this service to update members in a census to the values in the input JSON. Guest user access is enabled for this service.
-   **[InsCensusService:updateMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__updatememberswithplans.htm&language=en_US&type=5)**  
    Use this service to populate a census with primary members, their dependents, and their pre-enrolled plan.

Did this article solve your issue?

Let us know so we can improve!

YesNo