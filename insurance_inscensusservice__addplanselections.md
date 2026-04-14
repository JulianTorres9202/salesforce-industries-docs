---
title: "InsCensusService:addPlanSelections"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__addplanselections.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:addPlanSelections

InsCensusService:addPlanSelections[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:addPlanSelections

Use this service to insert pre-enrolled plans for each member specified in the input.

Important From Winter '23 onward, we have [InsCensusServiceStd:addPlanSelections](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addplanselections.htm&language=en_US&type=5 "Use this service to create GroupCensusMemberPlan records for existing GroupCensusMember records. It uses the ContractGroupPlans specified in the input JSON for adding plans to each GroupCensusMember. The service also accepts optional coverages per member such that primary members and dependents can be enrolled into different coverages under the same plan.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `addPlanSelections`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

-   The `ContractLineId__c` node contains the `ContractLineItem__c` Ids that the member is pre-enrolled in.
    
-   For each of `ContractLineItem__c` Id, the service evaluates whether the plan is valid for the member as follows:
    
    -   The `contractId` is valid for the `censusId`;
        
    -   The `ContractLineItem__c` Id is valid for the `contractId`;
        
    -   The product type of the `ContractLineItem__c` for the primary member isn’t equal to the product types listed in the primary member's `OptOutTypes__c`;
        
    -   The product type of the `ContractLineItem__c` for a dependent isn’t equal to the product types listed in the dependent's `OptOutTypes__c`, and the product type of the `ContractLineItem__c` isn’t be equal to the product types listed in the dependent's primary member's `OptOutTypes__c`.
        
-   The Ids of successfully created `GroupCensusMemberPlan__c` entries are returned.
    
-   The service also deletes newly created members (`isNewMember` is set to true in the JSON object) that don’t have entries in `GroupCensusMemberPlan__c` and when `onlySaveMembersWithValidProducts` is set to true.
    

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

Validates that the contractId belongs to the account/census.

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

JSON object with two nodes:

-   headers— The API name of contract line Id (`ContractLineId__c`).
    
-   members—List of members with plans to be inserted or updated. It must include the following two nodes:
    
    -   `Id` — The census member Id (`GroupCensusMember__c.Id`).
        
    -   `ContractLineId__c` — The list of the plans (`ContractLineItem__c.Id`) that the member is pre-enrolled in. The contract line items are delimited by semicolon(;).
        

 |
| 

`onlySaveMembersWithValidProducts`

 | 

Optional.

If true, new members without entries in `GroupCensusMemberPlan__c` are deleted. The default value is false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```
{  
   "censusId":"ID",
   "contractId":"ID",
   "onlySaveMembersWithValidProducts":true,
   "census":{  
      "headers":[  
         {  
            "name":"vlocity_ins__ContractLineId__c"
         },
      ],
      "members":[  
         {  
            "Id":"Census Member ID",
            "isNewMember":true,
            "vlocity_ins__ContractLineId__c": "ContractLineItem__c.Id;ContractLineItem__c.Id"
            
         },
         {  
            "Id":"Census Member ID",
            "isNewMember":true,
            "vlocity_ins__ContractLineId__c": "ContractLineItem__c.Id;ContractLineItem__c.Id"
         }
      ]
   },
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
            "vlocity_ins__ContractLineId__c": "a4D4P000000hbjSUAQ;a4D4P000000hbjSUAQ",
            "Id":"a4C4P000000d7POUAY"
         }
      ],
      "headers":[  
         {  
            "name":"vlocity_ins__ContractLineId__c"
         }
      ]
   }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the list of successfully inserted `GroupCensusMemberPlan__c` Ids. It also provides the list of errors encountered. These errors are grouped per member.

Here's the format of the output JSON:

```
{  
   "memberPlanIds":[  
      "GroupCensusMemberPlan__c.Id"
   ],
   "errors":[  
      {  
         "error":"error"
      }
   ]
}
```

The service returns an output JSON, formatted as per the following sample:

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
         "error":"ContractLineItem__c value is not valid:8004P000000zJKjQAM; Medical",
         "numPlans":2,
         "Id":"a4C4P000000ed6dUAA",
         "isNewMember":true,
         "vlocity_ins__ContractLineId__c":"8004P000000zJKjQAM;Medical"
      }
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo