---
title: "InsCensusService:getMembersWithPlans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmemberswithplans.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:getMembersWithPlans

InsCensusService:getMembersWithPlans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:getMembersWithPlans

Use this service to retrieve members of a census and their pre-enrolled plans. This service also retrieves field definitions for the `GroupCensusMember__c` and `GroupCensusMemberPlan__c` fields.

Important From Winter '23 onward, we have [InsCensusServiceStd:getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmemberswithplans.htm&language=en_US&type=5 "Use this service to retrieve the list of census members for a given censusId. Corresponding to these census members, the service retrieves the ContractGroupPlanIds from GroupCensusMemberPlan. The service also retrieves headers based on the fieldsetName and planFieldsetName.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `getMembersWithPlans`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service has two key functions:

1.  Retrieves the list of fields in  `GroupCensusMember__c` and `GroupCensusMemberPlan__c`.
    
    -   The service uses the parameter `fieldsetName` to retrieve the list of `GroupCensusMember__c` fields. If there is no value, fields are retrieved from the default fieldset that is `EditableTable`. If the entered value doesn't find a match no fields are retrieved.
        
    -   The service uses the parameter `planFieldsetName` to retrieve the list of  `GroupCensusMemberPlan__c` fields. If there is no value, all fields are retrieved. If the entered value doesn't find a match no fields are retrieved.
        
    -   If the `contractId` parameter has value, it populates `ContractLineId__c.options`  with the following details of the contract:
        
        -   Product name
            
        -   Product type
            
        -   Id of the plans which are a part of the contract.
            
    -   Retrieves relationship fields that are combined to form the JSON `headers` node:
        
        -   MemberIdentifier\_\_c
            
        -   PrimaryMemberIdentifier\_\_c
            
        -   RelatedCensusMemberId\_\_c
            
        -   IsPrimaryMember\_\_c
            
        -   IsSpouse\_\_c
            
        -   Id
            
2.  Retrieves the list of members in GroupCensusMember\_\_c.
    
    -   This service uses a `censusId` to retrieve census members from `GroupCensusMember__c` and census member plans from `GroupCensusMemberPlan__c`  for each member.
        
        Note
        
        The `offset` parameter value is used to retrieve the next 2000 `GroupCensusMember__c` rows (ordered by `GroupCensusMember__c` Id) after the offset.
        
        If there's no value for the `offset` parameter, the first 2000 rows are retrieved.
        
    -   The information retrieved for each member is based on the fields retrieved from  `GroupCensusMember__c` and `GroupCensusMemberPlan__c`.
        
    -   A list of members is placed into the `members` node.
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Options

 | 

Description

 |
| --- | --- |
| 

`censusId`

 | 

Required

Retrieves census with members.

 |
| 

`contractId`

 | 

Required

-   Id of Account's current contract.
    
-   Retrieves the product name, product type, and contract line item Id as options in the `ContractLineId__c` header field.
    

 |
| 

`planFieldsetName`

 | 

Optional

-   Retrieves `GroupCensusMemberPlan__c` and `GroupCensusMember__c` fields of the fieldset when there's a valid value.
    
-   No fields are returned if the value is not valid.
    
-   All `GroupCensusMemberPlan__c` fields are returned when there's no value.
    

 |
| 

`fieldsetName`

 | 

Optional

-   If it has a valid value, retrieves `GroupCensusMember__c` fields that are part of the fieldset.
    
-   If the value is not valid, no fields are returned.
    
-   If there is no value, retrieves `GroupCensusMember__c` fields that are part of the default fieldset (EditableTable)
    

 |
| 

`offset`

 | 

Optional

-   If it has no value, retrieves first 2000 GroupCensusMember\_\_c rows (ordered by Id).
    
-   If it has a valid value, it retrieves the next 2000  GroupCensusMember\_\_c rows (ordered by Id) after the offset . For example: If you have the following GroupCensusMember\_\_c rows
    
    Id Name
    
    aa1 Joe
    
    aa2 Ben
    
    aa 3 Hardy
    
    aa4 Ruth
    
    ....
    
    aa2000 Rex
    
    aa2001 Gina
    
    aa2002 Liz
    
    ....
    
    aa4000 Shin
    
    aa4001 Rob
    
    If no offset is specified. it retrieves rows 1 - 2000 (From Joe to Rex). If the offset is set to aa1, the rows retrieved would be rows 2 - 2001 (Ben to Gina). If the offset is set to aa2000, the rows retrieved would be rows 2001 - 4000 (Gina to Shin).
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON, formatted as per the example below:

```
{  
   "census":{  
      "members":[  
         {  
            "vlocity_ins__ContractLineId__c":"",
            "Id":"a4C4P000000dNdbUAE",
            "vlocity_ins__LastName__c":null,
            "vlocity_ins__FirstName__c":null,
            "vlocity_ins__Birthdate__c":"1999-08-08"
         },
         {  
            "vlocity_ins__ContractLineId__c":"a2N4P000006ygEjUAI",
            "Id":"a4C4P000000dNdcUAE",
            "vlocity_ins__LastName__c":null,
            "vlocity_ins__FirstName__c":null,
            "vlocity_ins__Birthdate__c":"1994-08-08"
         },
         {  
            "vlocity_ins__ContractLineId__c":"a2N4P000006ygEjUAI;a2N4P000006ygEiUAI",
            "Id":"a4C4P000000dNdeUAE",
            "vlocity_ins__LastName__c":null,
            "vlocity_ins__FirstName__c":null,
            "vlocity_ins__Birthdate__c":"1985-08-08"
         }
      ],
      "headers":[  
         {  
            "type":"STRING",
            "label":"First Name",
            "fieldId":"",
            "name":"vlocity_ins__FirstName__c"
         },
         {  
            "type":"DATE",
            "label":"Birthday",
            "fieldId":"",
            "name":"vlocity_ins__Birthdate__c"
         },
         {  
            "type":"STRING",
            "label":"Last Name",
            "fieldId":"",
            "name":"vlocity_ins__LastName__c"
         },
         {  
            "options":[  
               {  
                  "value":"a2N4P000006ygEiUAI",
                  "type":"Medical",
                  "name":"rootProd"
               },
               {  
                  "value":"a2N4P000006ygEjUAI",
                  "type":"Dental",
                  "name":"rootProd2"
               }
            ],
            "type":"REFERENCE",
            "label":"Plan",
            "fieldId":"",
            "name":"vlocity_ins__ContractLineId__c"
         }
      ]
   },
   "lastOffset" : "a4C4P000000dNdeUAE"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo