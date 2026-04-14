---
title: "InsCensusServiceStd:getMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:getMembers

InsCensusServiceStd:getMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:getMembers

Use this service to retrieve the members of a census from the `GroupCensusMember`. It also retrieves the headers based on the `fieldsetName`.

Class: ​`InsCensusServiceStd​`

Method: `getMembers`

The service accepts input in this format.

| censusId | fieldsetName | Offset | limit | searchKey |
| --- | --- | --- | --- | --- |
| c101 | test\_fieldset | cmember101 | integer | prefix |

The service uses input values to generate output that fits into your product model.

| census | lastOffSet |
| --- | --- |
| **headers** | **members** | Id of last census member |
| List of fields | List of Members |

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service has two key functions:

1.  Retrieves the list of `GroupCensusMember` fields and headers based on the `fieldetName`. The output always has `PrimaryGroupCensusMemberId`, `RelationshipToPrimaryMember`, `SourceSystemIdentifier`, and `PrimaryMemberSource` even if these fields are not included in the `fieldsetName`.
    
2.  The service uses `​censusId`​ to retrieve the list of census members from ​`GroupCensusMember​​` records.[](https://help.salesforce.com/s?language=en_US)
    1.  If the offset has value, it retrieves Primary `GroupCensusMember` rows (ordered by Id) after the offset and then retrieves all the dependents for these Primary Members.
    2.  If there is a limit value, the service retrieves the Primary `GroupCensusMember` rows (ordered by Id) not greater than the specified limit. It then retrieves all the dependents for these Primary Members. The limit can't be more than 500.
        
    3.  If `searchKey` has value, the service retrieves `GroupCensusMember` rows (ordered by Id) along with corresponding family, which have `searchKey` as a substring present in their `FirstName` or `LastName`.
        
    4.  If `memberIds` has a value, it retrieves `GroupCensusMember` rows (ordered by Id) whose Id is part of `memberIds` array. Either `memberIds` or `searchKey` has to be provided in input.
        
    5.  If `withPlans` is set to `true`, the service retrieves a list of selected plans for each member. The valid `ContractGroupPlanId` for each member are delimited by a semicolon and returned as a string.
        
    6.  The information retrieved for each member is based on the fields retrieved from `GroupCensusMember`.
        
    7.  The list of members is placed into the `members` node.
        

## Service Behavior

Understand how different inputs affect the service outputs.

| Input | Service Output |
| --- | --- |
| No `censusId` or invalid `censusId` | The service retrieves no census member. |
| No `fieldsetName` and valid `censusId` | 
-   If the `StandardFieldset` is present, the service takes it as the default field set and retrieves the list of `GroupCensusMember`.
-   If `StandardFieldset` is not present, the service consumes list of `GroupCensusMember` fields present in Editable table Fieldset and retrieves the list of `GroupCensusMember`.
-   If `StandardFieldset` and Editable Table Fieldset both are not present, the service throws an error.

 |
| Valid `fieldsetName` and valid `censusId` | The service retrieves the list of `GroupCensusMember` fields present in the given field set and the list of `GroupCensusMember`. |
| Valid `limit` | 

The service retrieves the list of `GroupCensusMember` within the specified limit. This list also includes dependents associated with the primary members.

 |
| Valid `offset` | 

The service retrieves the list of `GroupCensusMember`. This list also includes dependents associated with the primary members.

-   Id of each retrieved Primary `GroupCensusMember` is greater than offset.

 |
| Valid `offset` and valid `limit` | 

The service retrieves the list of `GroupCensusMember` fields present in the given field set and the list of `GroupCensusMember`.

-   Id of each retrieved Primary `GroupCensusMember` is greater than offset.
-   Number of retrieved Primary `GroupCensusMember` is less than or equal to the specified limit.
-   Retrieves dependents associated with the Primary `GroupCensusMember` in the list.
    

 |
| Valid `searchKey` | 

The service retrieves the list of `GroupCensusMember` fields present in the given field set and the list of `GroupCensusMember`. If the list has dependents, the service retrieves primary members corresponding to these dependents. All the members will contain `searchKey` as a substring in their `FirstName` or `LastName`.

 |
| Valid `searchKey` and valid `limit` | 

The service retrieves the list of `GroupCensusMember` fields present in the given field set and the list of `GroupCensusMember`. If the list has dependents, the service also retrieves primary members corresponding to these dependents. All the members will contain `searchKey` as a substring in their `FirstName` or `LastName`. Number of retrieved `GroupCensusMember` will not be greater than limit.

 |
| Valid `searchKey` and valid `offset` | 

The service retrieves the list of `GroupCensusMember` fields present in the given field set and the list of `GroupCensusMember`. If the list has dependents, the service also retrieves primary members corresponding to these dependents. All the members will contain `searchKey` as a substring in their `FirstName` or `LastName`. Id of each retrieved `GroupCensusMember` is greater than offset.

 |
| Valid `searchKey`, valid `limit` and valid `offset` | 

The service retrieves the list of `GroupCensusMember` fields present in the given field set and the list of `GroupCensusMember`.

-   All the members will contain `searchKey` as a substring in their `FirstName` or `LastName`.
-   Id of each retrieved `GroupCensusMember` is greater than offset.
-   Number of retrieved `GroupCensusMember` is less than or equal to the limit.
-   If the list has dependents, the service also retrieves primary members corresponding to these dependents.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| Options​ | ​Description​ |
| --- | --- |
| 
​​​`censusId`​​​

 | 

Required.​

Id of census whose members must be retrieved.

 |
| 

​​​

`fieldsetName​​​`

 | 

Optional. ​

Name of the field set to retrieve the `GroupCensusMember​​` fields.

If the value is invalid, the service returns no fields.

If there is no value, the service uses the default field set to retrieve ​​`GroupCensusMember`​​ fields.

 |
| 

`​limit​`

 | 

Optional.​

The number of census members to be retrieved. ​

 |
| 

​​​`offset​​​`

 | 

Optional​.

The ID of the census member after which the census members must be retrieved. ​

 |
| 

​`searchKey​`

 | 

A string to search for matching census member records.

 |

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON with a list of fields, list of members, and `lastOffSet` value.

```
{ 
   "census":{ 
      "members":[ 
         { 
            "Id":"a4C4P000000dNdbUAE",
            "LastName":member1,
            "FirstName":primary,
            "Birthdate":"1999-08-08"
         },
         { 
            "Id":"a4C4P000000dNdcUAE",
            "LastName":member1,
            "FirstName":dependent,
            "Birthdate":"1994-08-08"
         },
         { 
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
         }
      ]
   },
   "lastOffset" : "a4C4P000000dNdeUAE"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo