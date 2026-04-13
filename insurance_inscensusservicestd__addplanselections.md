---
title: "InsCensusServiceStd:addPlanSelections"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addplanselections.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusServiceStd:addPlanSelections

InsCensusServiceStd:addPlanSelections[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:addPlanSelections

Use this service to create `GroupCensusMemberPlan` records for existing `GroupCensusMember` records. It uses the `ContractGroupPlans` specified in the input JSON for adding plans to each `GroupCensusMember`. The service also accepts optional coverages per member such that primary members and dependents can be enrolled into different coverages under the same plan.

Class: ​`InsCensusServiceStd`​​

Method: `addPlanSelections`

Note

If the plan selections for every member are uploaded using CSV, use the `InsCensusServiceStd:updateMembersWithPlans` service.

GroupCensus and Contract must have the same group account.

ContractGroupPlan status must be active.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service uses `censusId` and `contractId` to insert members' selected plans.

1.  For each of its `ContractGroupPlan` IDs, the service evaluates whether the plan is valid for the member based on these factors:
    -   The `contractId` is valid for the `censusId`.
        
    -   The ​`ContractGroupPlan`​​ Id is valid for the ​`contractId​`.
    -   `IsOptOutAllPlans` is false.
        
    -   When ContractGroupPlan has record type as Product (ContractGroupPlan of parent):
        
        -   The product type of the ​​`ContractGroupPlan`​​ for the primary member must not be equal to the product types listed in the primary member's ​`OptOutPlanTypes`​​.
            
        -   The product type of the ​​`ContractGroupPlan​​` for a dependent must not be equal to the product types listed in the dependent's ​`OptOutPlanTypes`​​, and the product type of the ​`ContractGroupPlan`​​ must not be equal to the product types listed in the ​`OptOutPlanTypes`​​ of dependent's primary member.
            
    -   When ContractGroupPlan has record type as CoverageSpec (ContractGroupPlan of child):
        
        -   The product type of the ​​`ContractGroupPlan`​​ of a child for the primary member must not be equal to the product types listed in the primary member's ​`OptOutPlanTypes`​​.
            
        -   The product type of the ​​`ContractGroupPlan​​` of a child for a dependent must not be equal to the product types listed in the dependent's ​`OptOutPlanTypes`​​, and the product type of the ​`ContractGroupPlan`​​ must not be equal to the product types listed in the ​`OptOutPlanTypes`​​ of dependent's primary member.
            
2.  The Ids of successfully created `GroupCensusMemberPlan` entries are returned for valid plans.
    
3.  The service retrieves the valid plans for eligible group classes for the given contract. Enrollment in a root plan and its coverages depends on whether the member's class is eligible for the plan, and if the plan accepts members not associated with any class.
    
    If the service determines that a census member can enroll in a plan, the plan is added to the `GroupCensusMemberPlan`.
    
    -   A plan is added to a `GroupCensusMemberPlan` if:
        
        -   A census member is associated with a valid group class and a `ContractGroupPlanGroupClass` record exists with the group class and the plan.
            
        -   A census member is associated with a valid group class, no `ContractGroupPlanGroupClass` record exists for the group class, and the plan doesn't exist for any other group class.
            
        -   A census member is not associated with a valid group class and no `ContractGroupPlanGroupClass` record exists with the plan.
            
    -   A plan is not added to a `GroupCensusMemberPlan` if:
        
        -   A census member is associated with a valid group class, no `ContractGroupPlanGroupClass` record exists for the group class, but the plan does exist for another group class.
            
        -   A census member is not associated with a valid group class and a `ContractGroupPlanGroupClass` record exists with the plan and group classes.
            
4.  When invalid `contractGroupPlanIds` are passed for a `groupCensusMember` (the flag `isNewMember` is true), the service deletes the `groupCensusMember` records and doesn't create any new `GroupCensusMemberPlan` records for the `groupCensusMember`. Expect this output only when the flag `onlySaveMembersWithValidProducts` is set true in the JSON object.
    

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

Required.

Id of census with the members whose plans must be inserted.

Validates that the `contractId` belongs to the account/census.

 |
| 

`contractId`

 | 

Required.

Id of Account's current contract.

Validates that the plans for each member are part of the contract.

 |
| 

`census`

 | 

Required.

JSON input with two nodes:

-   headers— List of field API names of `GroupCensusMemberPlan`.
    
-   members—List of members with plans to be inserted or updated. It must include the following nodes:
    
    -   `Id` — The census member Id.
        
    -   `isNewMember` - True if the member is newly inserted
        
    -   `ContractGroupPlan` - The list of selected plans for the member. Delimit the contract group plan IDs by a semicolon (;).
        

 |
| 

`onlySaveMembersWithValidProducts`

 | 

Optional.

If true, new members without entries in `GroupCensusMemberPlan` are deleted. The default value is false.

 |

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| No `censusId` or invalid `censusId` | The service adds no member plan. |
| No `contractId` or invalid `contractId` | The service adds no member plan. |
| Invalid `contractId` for the census specified | The service adds no member plan. |
| No rows to insert/update | The service adds no member plan. |
| Row has no ID (`GroupCensusMember.Id`) | The service adds no member plan. |
| Invalid `ContractGroupPlanId` for the contract specified | 
The service creates no member plan.

If `onlySaveMembersWithValidProducts` is true and the member is new, the service does the following:

-   Deletes the member with no valid plans.
-   Creates a member if it has at least one valid plan.

 |
| Invalid `ContractGroupPlanId` for the member (due to opt-out) | 

Member plan is not created

If `onlySaveMembersWithValidProducts` is true and the member is new, the service does the following:

-   Deletes the member with no valid plans.
-   Creates a member if it has at least one valid plan.

 |
| The primary member opts out of a product type | 

`IsOptOutAllPlans` takes precedence, followed by `OptOutPlanTypes`.

-   If `IsOptOutAllPlans` = true, the service doesn't create a member plan even if you specify a product for enrollment.
-   If `IsOptOutAllPlans` = false and a product is specified for member enrollment, but its product type is the same as the opt-out entry, then the service doesn't create a member plan.
-   If IsOptOutAllPlans = false and coverage is specified for member enrollment with the parent product type same as the opt-out entry, the service doesn't create a member plan.

If the primary member opts out of a product type, the dependents also opt out of that product type.

 |
| Dependent member opts out of a product type | 

`IsOptOutAllPlans` takes precedence, followed by `OptOutPlanTypes`

-   If `IsOptOutAllPlans` = true, the service doesn't create a member plan even if you specify a product for enrollment.
-   If `IsOptOutAllPlans` = false and a product is specified for member enrollment, but if its product type is the same as the opt-out entry, the service doesn't create a member plan.
-   If IsOptOutAllPlans = false and coverage is specified for member enrollment with the parent product type same as the opt-out entry, the service doesn't create a member plan.
    

If the primary member opts out of a product type, the dependents also opt out of that product type.

If `IsOptOutAllPlans` = true for a primary member, the same output is applicable for the associated dependents.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```
{ 
   "censusId":"ID",
   "contractId":"ID",
   "census":{ 
      "headers":[ 
         { 
            "name":"GroupCensusMemberPlan.fieldAPI1"
         },
         { 
            "name":"GroupCensusMemberPlan.fieldAPI2"
         }
      ],
      "members":[ 
         { 
            "Id":"Census Member ID",
            "isNewMember":true,
            "GroupCensusMemberPlan.fieldAPI1":"value1",
            "GroupCensusMemberPlan.fieldAPI2":"value2",
            "ContractGroupPlanId": "ContractGroupPlan.Id;ChildContractGroupPlan.Id"
         },
         { 
            "Id":"Census Member ID",
            "isNewMember":true,
            "GroupCensusMemberPlan.fieldAPI1":"value1",
            "GroupCensusMemberPlan.fieldAPI2":"value2",
            "ContractGroupPlanId": "ContractGroupPlan.Id;ChildContractGroupPlan.Id"
         }
      ]
   },
   "onlySaveMembersWithValidProducts" : true
}
```

Here's an example of the input JSON:

```
{ 
   "censusId":"a4D4P000000hbjSUAQ",
   "contractId":"8004P000000zF2dQAE",
   "census":{ 
      "members":[ 
         { 
            "ContractGroupPlanId":"a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ",
            "Id":"a4C4P000000d7POUAY"
         }
      ],
      "headers":[ 
         { 
            "name":"ContractGroupPlanId"
         }
      ]
   }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the list of successfully inserted `GroupCensusMemberPlan` Ids. It also provides the list of errors encountered. These errors are grouped per member.

Here's the format of the output JSON:

```
{ 
   "memberPlanIds":[ 
      "GroupCensusMemberPlan.Id"
   ],
   "errors":[ 
      { 
         "error":"error"
      }
   ]
}
```

The service returns an output JSON, formatted like this:

```
{ 
   "memberPlanIds":[ 
      "a4B4P000006jKsMUAU",
      "a4B4P000006jKsNUAU",
      "a4B4P000006jKsOUAU",
      "a4B4P000006jKsPUAU"
   ],
   "errors":[ 
      { 
         "numPlansError":2,
         "error":"ContractGroupPlan value is not valid:8004P000000zJKjQAM; Medical",
         "numPlans":2,
         "Id":"a4C4P000000ed6dUAA",
         "isNewMember":true,
         "ContractGroupPlan":"8004P000000zJKjQAM;Medical"
      }
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo