---
title: "InsCensusServiceStd:getMembersWithPlans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmemberswithplans.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:getMembersWithPlans

InsCensusServiceStd:getMembersWithPlans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:getMembersWithPlans

Use this service to retrieve the list of census members for a given `censusId`. Corresponding to these census members, the service retrieves the `ContractGroupPlanIds` from `GroupCensusMemberPlan`. The service also retrieves headers based on the `fieldsetName` and `planFieldsetName`.

Class: ​`InsCensusServiceStd`​​

Method: `getMembersWithPlans`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service has two key functions:

1.  Retrieves the list of fields in ​​`GroupCensusMember`​ and ​`GroupCensusMemberPlan`​​.
    -   The service uses the parameter `​fieldsetName`​ to retrieve the list of ​`GroupCensusMember​​` fields. If there is no value, fields are retrieved from the default field set. If the entered value doesn't find a match, no fields are retrieved.
        
    -   The service uses the parameter ​`planFieldsetName​` to retrieve the list of ​`GroupCensusMemberPlan`​​ fields. If there is no value, all fields are retrieved. If the entered value doesn't find a match no fields are retrieved.
        
    -   Retrieves relationship fields that are combined to form the JSON ​headers​​ node even if these fields are not included in the `fieldsetName`. These fields are: `PrimaryGroupCensusMemberId`, `RelationshipToPrimaryMember`, `SourceSystemIdentifier`, and `PrimaryMemberSource`.
        
    -   If the `` `contractGroupPlanId` `` parameter has value, it populates the list of contract line records with the following details of the contract:
        
        -   Contract Group Plan name
            
        -   Product Type
            
        -   Id of the contract group plans
            
2.  The service uses ​`censusId`​ to retrieve the list of census members from ​`GroupCensusMember`​​ records and contract group plans from `GroupCensusMemberPlan` for each member.
    
    -   If the offset has value, it retrieves Primary `GroupCensusMember` rows (ordered by Id) after the offset and then retrieves all the dependents for these Primary Members.
        
    -   If there is a limit value, the service retrieves the Primary `GroupCensusMember` rows (ordered by Id) not greater than the specified limit. It then retrieves all the dependents for these Primary Members. The limit can't be more than 500.
        
    -   If `searchKey` has value, the service retrieves `GroupCensusMember` rows (ordered by Id) along with corresponding family, which has `searchKey` as a substring present in their `FirstName` or `LastName`. If `GroupCensusMember` contains dependents, then service retrieves primary members corresponding to those dependents.
        
    -   If `memberIds` has a value, it retrieves `GroupCensusMember` rows (ordered by Id) whose Id is part of `memberIds` array. Either `memberIds` or `searchKey` has to be provided in input.
        
    -   The information retrieved for each member is based on the fields retrieved from `GroupCensusMember` and `GroupCensusMemberPlan`.
        
    -   The list of members is placed into the ​​`members`​​ node.
        

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| 
No `censusId` or invalid `censusId`

 | The service retrieves no census member. |
| No `fieldsetName` and valid `censusId` | 

The service retrieves:

-   If `StandardFieldset` is present, the service takes the list of `GroupCensusMember` fields present in Standard Fieldset and retrieves the list of `GroupCensusMember` with ContractGroupPlanIds.
-   If Standard Fieldset is not present, the service takes the list of `GroupCensusMember` fields present in Editable table Fieldset and retrieves the list of `GroupCensusMember` with ContractGroupPlanIds.
    
-   If StandardFieldset and Editable Table Fieldset both are not present, the service throws an error.

 |
| Valid `fieldsetName` and valid `censusId` | The service lists `GroupCensusMember` fields as per the specified `fieldsetName` and retrieves the list of `GroupCensusMember` with `ContractGroupPlanIds`. |
| No `planFieldsetName` valid `fieldsetName` and valid `censusId` | The service lists `GroupCensusMember` fields as per the specified `fieldsetName`, `ContractGroupPlanId` and Name field of `GroupCensusMemberPlan`. It retrieves list of `` `GroupCensusMember` `` with `ContractGroupPlanIds`. |
| Valid `planFieldsetName` valid `fieldsetName` and valid `censusId` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified fieldsetName.
    
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`.
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    

 |
| Valid `contractId` | The service retrieves the contract group plan name, product type, child products, and contract group plan Id as options in the `ContractGroupPlanId` header field. |
| Valid `limit` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified fieldsetName.
    
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`.
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    
-   Number of retrieved Primary `GroupCensusMember` is less than or equal to the limit.
    
-   Dependents associated with the Primary `GroupCensusMember` in the list.
    

 |
| Valid `offset` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified `fieldsetName`.
    
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`.
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    
-   Id of each retrieved Primary `GroupCensusMember` is greater than offset.
    
-   Dependents associated with the Primary `GroupCensusMember` in the list.
    

 |
| Valid `offset` and valid `limit` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified `fieldsetName`.
    
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`.
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    
-   Number of retrieved Primary `GroupCensusMember` is less than or equal to the limit.
    
-   Dependents associated with the Primary `GroupCensusMember` in the list.
    
-   Id of each retrieved Primary `GroupCensusMember` is greater than offset.
    

 |
| Valid `searchKey` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified fieldsetName.
    
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    
-   If the list has dependents, the service retrieves primary members corresponding to these dependents.
    
-   All the members will contain a `searchKey` as substring in their `FirstName` or `LastName`.
    

 |
| Valid `searchKey` and valid `limit` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified fieldsetName.
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`.
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    
-   If the list has dependents, the service retrieves primary members corresponding to these dependents.
    
-   All the members will contain a `searchKey` as substring in their `FirstName` or `LastName`.
    
-   Number of retrieved `GroupCensusMember` is less than or equal to the specified limit.
    

 |
| Valid `searchKey` and valid `offset` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified `fieldsetName`.
    
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`.
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    
-   If the list has dependents, the service retrieves primary members corresponding to these dependents.
    
-   All the members will contain a `searchKey` as substring in their `FirstName` or `LastName`.
    
-   Id of each retrieved `GroupCensusMember` is greater than offset.
    

 |
| Valid `searchKey`, valid `limit` and valid `offset` | 

The service retrieves:

-   `GroupCensusMember` fields as per the specified `fieldsetName`.
    
-   `GroupCensusMemberPlan` fields as per the specified `planFieldsetName`.
    
-   List of `GroupCensusMember` with `ContractGroupPlanIds`.
    
-   If the list has dependents, the service retrieves primary members corresponding to these dependents.
    
-   All the members will contain a `searchKey` as substring in their `FirstName` or `LastName`.
    
-   Number of retrieved `GroupCensusMember` is less than or equal to the specified limit.
    
-   Id of each retrieved `GroupCensusMember` is greater than offset.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| Options​ | ​Description​ |
| --- | --- |
| 
`​​​censusId​​​`

 | 

Required.​

Id of census whose members must be retrieved.

 |
| 

​​​`contractId`

 | 

​Required​​​.

Id of Account's current contract.​​​

Retrieves the contract group plan name, product type, and contract group

 |
| 

​​​

`fieldsetName​​​`

 | 

Optional. ​

Name of field set to retrieve the GroupCensusMember​​ fields.

If the value is invalid, the service returns no fields.

If there is no value, the service uses the default field set to retrieve ​​GroupCensusMember​​ fields.

 |
| 

​​​`planFieldsetName​​​`

 | 

Optional.

​​​Retrieves ​GroupCensusMemberPlan​ and ​GroupCensusMember​​ fields when there's a valid plan field set value.​​​

No fields are returned if the value is not valid.​​​

All ​​GroupCensusMemberPlan​​ fields are returned when there's no value.​​​

 |
| 

`​limit​`

 | 

Optional.​

The number of census members to be retrieved. ​

 |
| 

`​​​offset​​​`

 | 

Optional​.

The ID of the census member after which the census members must be retrieved. ​

 |
| 

`​searchKey​`

 | 

A string to search for matching census member records.

 |

## Input JSON

This service does not take an input JSON. ​

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON formatted as per the example below. The output has details for the members in the census, where ​headers​ is a list of field API names of `GroupCensusMember` and `GroupCensusMemberPlan`. The `members`​​ node ​returns list of selected plans for the member along with the ContractGroupPlanId delimited by ;. The `lastOffset` field shows the ID of the last census member which is retrieved. This value can be used as the offset parameter to get the next rows.

Here's the sample output JSON format:

```json
{ 
   "census":{ 
      "members":[ 
         { 
            "ContractGroupPlanId":"ID1;ID2",
            "Id":"ID",
            "fieldAPI1":"value"
         }
      ],
      "headers":[ 
         { 
            "type":"field type",
            "label":"field label",
            "fieldId":"",
            "name":"fieldAPI1"
         },
         { 
            "options":[ 
               { 
                  "value":"ID",
                  "type":"Product Type",
                  "name":"Contract Group Plan Name"
               }
            ],
            "type":"REFERENCE",
            "label":"Plan",
            "fieldId":"",
            "name":"ContractGroupPlanId"
         }
      ]
   },
   "lastOffset" : "census member Id"
}
```

Here's the sample output JSON:

```json

{ 
   "census":{ 
      "members":[ 
         { 
            "ContractGroupPlanId":"",
            "Id":"a4C4P000000dNdbUAE",
            "LastName":member1,
            "FirstName":primary,
            "Birthdate":"1999-08-08"
         },
         { 
            "ContractGroupPlanId":"a2N4P000006ygEjUAI",
            "Id":"a4C4P000000dNdcUAE",
            "LastName":member1,
            "FirstName":dependent,
            "Birthdate":"1994-08-08"
         },
         { 
            "ContractGroupPlanId":"a2N4P000006ygEjUAI;a2N4P000006ygEiUAI",
            "Id":"a4C4P000000dNdeUAE",
            "LastName":member2,
            "FirstName":primary,
            "Birthdate":"1985-08-08"
         }
      ],
      "headers":[ 
         { 
            "type":"STRING",
            "label":"First Name",
            "fieldId":"",
            "name":"FirstName"
         },
         { 
            "type":"DATE",
            "label":"Birthday",
            "fieldId":"",
            "name":"Birthdate"
         },
         { 
            "type":"STRING",
            "label":"Last Name",
            "fieldId":"",
            "name":"LastName"
         },
         { 
            "type":"REFERENCE",
            "label":"Plan",
            "fieldId":"",
            "name":"ContractGroupPlanId",
             "options":[
               {
                    "value":"a2N4P000006ygEiUAI",
                    "type":"Medical",
                    "name":"rootProd",
                    "childProducts": [
                        {
                            "value": "0rgDC000000000RYAQ",
                            "IsOptional": false,
                            "name": "MandatoryCoverage"
                        },
                        {  
                            "value": "0rgDC000000000RYBQ",
                            "IsOptional": true,
                            "name": "OptionalCoverage"
                        }
                    ]
                },
                {
                    "value":"a2N4P000006ygEjUAI",
                    "type":"Dental",
                    "name":"rootProd2",
                    "childProducts": [
                        {
                            "value": "0rgDC000000000RYCQ",
                            "IsOptional": false,
                            "name": "MandatoryCoverage"
                        },
                        {
                            "value": "0rgDC000000000RYDQ",
                            "IsOptional": true,
                            "name": "OptionalCoverage"
                        }
                    ]
                }
            ]
         }
      ]
   },
   "lastOffset" : "a4C4P000000dNdeUAE"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo