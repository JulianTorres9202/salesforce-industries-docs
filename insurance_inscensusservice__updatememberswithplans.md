---
title: "InsCensusService:updateMembersWithPlans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__updatememberswithplans.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:updateMembersWithPlans

InsCensusService:updateMembersWithPlans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:updateMembersWithPlans

Use this service to populate a census with primary members, their dependents, and their pre-enrolled plan.

Important From Winter '23 onward, we have [InsCensusServiceStd:updateMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatememberswithplans.htm&language=en_US&type=5 "Use this service to populate a group census with primary members, their dependents, and their pre-enrolled plan. This service updates existing GroupCensusMember by memberKey and creates GroupCensusMemberPlan records for existing GroupCensusMember records. It uses the ContractGroupPlans specified in the input JSON to update plans for each GroupCensusMember.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `updateMembersWithPlans`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

-   The service calls `updateMembers` to save data about the members, parsing through the members in the JSON object and adding an Id and `isNewMember` for each one.
    
-   The service then calls `addPlanSelections` to save members' pre-enrolled plans.
    
-   If `isNewMember` is set to true, `addPlanSelections` deletes any newly created members that do not have entries in `GroupCensusMemberPlan__c` and if `onlySaveMembersWithValidProducts` parameter is set to true.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusId` 

 | 

Required

Id of census where members to be uploaded belong or will belong.

Used to validate that the contractId belongs to the account/census.

 |
| 

`contractId` 

 | 

Required

Id of Account's current contract.

Used to validate that the plans of each member is part of the contract.

 |
| 

`onlySaveMembersWithValidProducts`

 | 

Boolean

if true, new members without entries in `GroupCensusMemberPlan__c` are deleted.

 |
| 

`duplicateKeys`

 | 

Stringified list

List of fieldAPI names of `GroupCensusMember__c`

Used to determine which members already exist in the table, in which case an update is executed instead of an insert.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's what the format looks like for the input JSON:

```
{
   "censusId":"a4D4P000000hbjSUAQ",
   "contractId":"a4D4P000000yujQER",
   "onlySaveMembersWithValidProducts":true,
   "census":{
      "headers":[
         {
            "name":"vlocity_ins__FirstName__c"
         },
         {
            "name":"vlocity_ins__LastName__c"
         },
         {
            "name":"vlocity_ins__IsPrimaryMember__c"
         },
         {
            "name":"vlocity_ins__IsSpouse__c"
         },
         {
            "name":"vlocity_ins__MemberIdentifier__c"
         },
         {
            "name":"vlocity_ins__PrimaryMemberIdentifier__c"
         },
         {
            "name":"Id"
         },
         {
            "name":"vlocity_ins__ContractLineId__c"
         },
         {
            "name":"vlocity_ins__IsOptOut__c"
         },
         {
            "name":"vlocity_ins__OptOutTypes__c"
         }
      ],
      "members":[
         {
            "vlocity_ins__FirstName__c":"Maurice",
            "vlocity_ins__LastName__c":"Johnson",
            "vlocity_ins__IsPrimaryMember__c":true,
            "vlocity_ins__IsSpouse__c":false,
            "vlocity_ins__MemberIdentifier__c":"Maurice",
            "vlocity_ins__PrimaryMemberIdentifier__c":null,
            "vlocity_ins__ContractLineId__c":"a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ",
            "vlocity_ins__IsOptOut__c" : false,
            "vlocity_ins__OptOutTypes__c" :null
         },
         {
            "vlocity_ins__FirstName__c":"Lizzy",
            "vlocity_ins__LastName__c":"Johnson",
            "vlocity_ins__IsPrimaryMember__c":false,
            "vlocity_ins__IsSpouse__c":false,
            "vlocity_ins__MemberIdentifier__c":"Lizzy",
            "vlocity_ins__PrimaryMemberIdentifier__c":"Maurice",
            "vlocity_ins__ContractLineId__c":"a4D4P000000hbjSUAQ",
            "vlocity_ins__IsOptOut__c" :true,
            "vlocity_ins__OptOutTypes__c" :null
         },
         {
            "vlocity_ins__FirstName__c":"Jamie",
            "vlocity_ins__LastName__c":"Johnson",
            "vlocity_ins__IsPrimaryMember__c":false,
            "vlocity_ins__IsSpouse__c":true,
            "vlocity_ins__MemberIdentifier__c":"Jamie",
            "vlocity_ins__PrimaryMemberIdentifier__c":"Maurice",
            "vlocity_ins__ContractLineId__c":"a4D4P000000hbjSUAQ",
            "vlocity_ins__IsOptOut__c" : false,
            "vlocity_ins__OptOutTypes__c" :"Medical"
         },
         {
            "vlocity_ins__FirstName__c":"Bella",
            "vlocity_ins__LastName__c":"James",
            "vlocity_ins__IsPrimaryMember__c":true,
            "vlocity_ins__IsSpouse__c":false,
            "vlocity_ins__MemberIdentifier__c":"Bella",
            "vlocity_ins__PrimaryMemberIdentifier__c":null,
            "vlocity_ins__ContractLineId__c":null,
            "vlocity_ins__IsOptOut__c" :true,
            "vlocity_ins__OptOutTypes__c" :null
         }
      ]
   },
   "duplicateKeys" : [
      "vlocity_ins__FirstName__c",
      "vlocity_ins__LastName__c"
   ]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here is a sample output JSON:

```
{  
   "errors":[  
      {  
         "error":"ContractLineItem__c value is not valid:8004P000000zJKjQAM; Medical",
         "vlocity_ins__FirstName__c":"Maurice",
         "vlocity_ins__LastName__c":"Johnson",
         "vlocity_ins__IsPrimaryMember__c":true,
         "vlocity_ins__IsSpouse__c":false,
         "vlocity_ins__MemberIdentifier__c":"Maurice",
         "vlocity_ins__PrimaryMemberIdentifier__c":null
      }
   ],
   "censusMemberIds":[  
      "a4C4P000000ed6dUAA",
      "a4C4P000000ed6eUAA",
      "a4C4P000000ed6fUAA"
   ],
   "memberPlanIds":[  
      "a4B4P000006jKsMUAU",
      "a4B4P000006jKsNUAU",
      "a4B4P000006jKsOUAU",
      "a4B4P000006jKsPUAU"
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo