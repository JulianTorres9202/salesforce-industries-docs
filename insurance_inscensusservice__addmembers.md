---
title: "InsCensusService:addMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__addmembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:addMembers

InsCensusService:addMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:addMembers

Use this service to add members to a census via an input JSON. Guest user access is enabled for this service.

Important From Winter '23 onward, we have [InsCensusServiceStd:addMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addmembers.htm&language=en_US&type=5 "Use this service to add group census members to a group census using an input JSON.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `addMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service takes the members in an input JSON, adds them to the given `censusId`, and outputs a list of the Ids of the added members (`censusMemberIds`).

[](https://help.salesforce.com/s?language=en_US)Note

If the members list contains primary members and dependents, the input must have all of the members' id (vlocity\_ins\_\_MemberIdentifier\_\_c). All the values should be unique.

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

Id of the census to add members to.

 |
| 

`census`

 | 

Required.

Input JSON of the members to be added.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The input JSON includes `headers`, which lists the fields to be added or set; and `members`, which list members with their corresponding field-value pairs.

```
{
    "headers": [
        {
            "type": "STRING",
            "label": "Last Name",
            "fieldId": "",
            "name": "vlocity_ins__LastName__c"
        },
        {
            "type": "STRING",
            "label": "First Name",
            "fieldId": "",
            "name": "vlocity_ins__FirstName__c"
        },
        {
            "type": "DOUBLE",
            "label": "FTE",
            "fieldId": "",
            "name": "vlocity_ins__FTE__c"
        },
        {
            "type": "PICKLIST",
            "label": "Gender",
            "fieldId": "",
            "name": "vlocity_ins__Gender__c"
        },
        {
            "type": "DATE",
            "label": "Birthday",
            "fieldId": "",
            "name": "vlocity_ins__Birthdate__c"
        },
        {
            "type": "BOOLEAN",
            "label": "Is Spouse",
            "fieldId": "",
            "name": "vlocity_ins__IsSpouse__c"
        },
        {
            "type": "BOOLEAN",
            "label": "Primary",
            "fieldId": "",
            "name": "vlocity_ins__IsPrimaryMember__c"
        },
        {
            "type": "REFERENCE",
            "label": "Group Class",
            "fieldId": "",
            "name": "vlocity_ins__GroupClassId__c"
        },
        {
            "type": "STRING",
            "label": "Primary Member Identifier",
            "fieldId": "",
            "name": "vlocity_ins__PrimaryMemberIdentifier__c"
        },
        {
            "type": "STRING",
            "label": "Member Identifier",
            "fieldId": "",
            "name": "vlocity_ins__MemberIdentifier__c"
        },
        {
            "type": "EMAIL",
            "label": "Email",
            "fieldId": "",
            "name": "vlocity_ins__Email__c"
        }
    ],
    "members": [
        {
            "vlocity_ins__LastName__c": "Robbins",
            "vlocity_ins__FirstName__c": "Timmy",
            "vlocity_ins__FTE__c": 1,
            "vlocity_ins__Gender__c": "Male",
            "vlocity_ins__Birthdate__c": "1985-12-13",
            "vlocity_ins__IsSpouse__c": true,
            "vlocity_ins__IsPrimaryMember__c": true,
            "vlocity_ins__GroupClassId__c": "a3yf4000000LdtrAAC",
            "vlocity_ins__MemberIdentifier__c": "1",
	             "vlocity_ins__PrimaryMemberIdentifier__c": null,
	             "vlocity_ins__Email__c": "test@vlocity.com"
        },
        {
            "vlocity_ins__LastName__c": "Robbins",
            "vlocity_ins__FirstName__c": "Jason",
            "vlocity_ins__FTE__c": 1,
            "vlocity_ins__Gender__c": "Male",
            "vlocity_ins__Birthdate__c": "1985-10-13",
            "vlocity_ins__IsSpouse__c": true,
            "vlocity_ins__IsPrimaryMember__c": true,
            "vlocity_ins__GroupClassId__c": "a3yf4000000LdtrAAC",
            "vlocity_ins__MemberIdentifier__c": "2",
	             "vlocity_ins__PrimaryMemberIdentifier__c": null,
	             "vlocity_ins__Email__c": "test1@vlocity.com"
        }
    ]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service does not produce an output JSON. If any of the entries have errors, those are listed in the output.

```
{  
   "errors":[  
      {  
	      "error":"Birthdate is invalid",
            "vlocity_ins__LastName__c": "Robbins",
            "vlocity_ins__FirstName__c": "Jason",
            "vlocity_ins__FTE__c": 1,
            "vlocity_ins__Gender__c": "Male",
            "vlocity_ins__Birthdate__c": "1985-10-13",
            "vlocity_ins__IsSpouse__c": true,
            "vlocity_ins__IsPrimaryMember__c": true,
            "vlocity_ins__GroupClassId__c": "a3yf4000000LdtrAAC",
            "vlocity_ins__MemberIdentifier__c": "2",
	             "vlocity_ins__PrimaryMemberIdentifier__c": null,
	             "vlocity_ins__Email__c": "test1@vlocity.com"
        }
   ],
   "censusMemberIds":[  
      "a4C4P000000ed6dUAA"
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo