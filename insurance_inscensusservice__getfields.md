---
title: "InsCensusService:getFields"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getfields.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:getFields

InsCensusService:getFields[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:getFields

Use this service to retrieve field definitions and field API names for group census members and group census plans. Guest user access is enabled for this service.

Important From Winter '23 onward, we have [InsCensusServiceStd:getFields](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getfields.htm&language=en_US&type=5 "Use this service to retrieve field definitions and field API names for group census members and group census member plans.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `getFields`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

-   The service retrieves the list of `GroupCensusMember__c` fields.
    
-   If the `withPlans` parameter is set to true, the service also retrieves the list of `GroupCensusMemberPlan__c` fields.
    
-   The list of fields definitions are combined to form the `headers` JSON node.
    
    -   If `GroupClassId` `__c` is included in the list of fields retrieved, an additional node is added under the headers - `GroupClassId__r.Name`.
        
-   The list of field API names are combined to form the `fields` JSON node.
    
    -   If `GroupClassId` `__c` is included in the list of fields retrieved, an additional node is added under the fields - `GroupClassId__r.Name`.
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`fieldsetName`

 | 

Retrieves `GroupCensusMember__c` fields that are part of the field set for any valid values.

No fields returned for values with no field sets.

Default = EditableTable

 |
| 

`planFieldsetName`

 | 

Retrieves `GroupCensusMemberPlan__c` fields that are part of the field set for any valid values.

-   No fields returned for values with no field sets.
    
-   All `GroupCensusMemberPlan__c` fields returned if fields contain no values.
    

 |
| 

`withPlans`

 | 

Boolean

If `true`, includes fields from `GroupCensusMemberPlan__c`.

Default = `false`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON formatted as per the example below:

```
{
  "fields": [
    "Name",
    "vlocity_ins__Birthdate__c",
    "vlocity_ins__FirstName__c",
    "vlocity_ins__Gender__c",
    "vlocity_ins__LastName__c",
    "vlocity_ins__RelatedCensusMemberId__c",
    "vlocity_ins__IsPrimaryMember__c",
    "vlocity_ins__IsSpouse__c",
    "vlocity_ins__MemberIdentifier__c",
    "vlocity_ins__PrimaryMemberIdentifier__c"
  ],
  "headers": [
    {
      "type": "STRING",
      "label": "Name",
      "fieldId": "",
      "name": "Name"
    },
    {
      "type": "DATE",
      "label": "Birthdate",
      "fieldId": "",
      "name": "vlocity_ins__Birthdate__c"
    },
    {
      "type": "STRING",
      "label": "First Name",
      "fieldId": "",
      "name": "vlocity_ins__FirstName__c"
    },
    {
      "options": [
        {
          "value": "Male",
          "label": "Male"
        },
        {
          "value": "Female",
          "label": "Female"
        }
      ],
      "type": "PICKLIST",
      "label": "Gender",
      "fieldId": "",
      "name": "vlocity_ins__Gender__c"
    },
    {
      "type": "STRING",
      "label": "Last Name",
      "fieldId": "",
      "name": "vlocity_ins__LastName__c"
    },
    {
      "type": "REFERENCE",
      "label": "Primary Census Member",
      "fieldId": "",
      "name": "vlocity_ins__RelatedCensusMemberId__c"
    },
    {
      "type": "BOOLEAN",
      "label": "Primary",
      "fieldId": "",
      "name": "vlocity_ins__IsPrimaryMember__c"
    },
    {
      "type": "BOOLEAN",
      "label": "Is Spouse",
      "fieldId": "",
      "name": "vlocity_ins__IsSpouse__c"
    },
    {
      "type": "STRING",
      "label": "Member Identifier",
      "fieldId": "",
      "name": "vlocity_ins__MemberIdentifier__c"
    },
    {
      "type": "STRING",
      "label": "Primary Member Identifier",
      "fieldId": "",
      "name": "vlocity_ins__PrimaryMemberIdentifier__c"
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo