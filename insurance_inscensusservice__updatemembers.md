---
title: "InsCensusService:updateMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__updatemembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:updateMembers

InsCensusService:updateMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:updateMembers

Use this service to update members in a census to the values in the input JSON. Guest user access is enabled for this service.

Important From Winter '23 onward, we have [InsCensusServiceStd:updateMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatemembers.htm&language=en_US&type=5 "Use this service to update the values of existing members in a census.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `updateMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service takes the members from an input JSON and updates the census (as per the given `censusId`) with the new data.

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

Id of the census with members to update.

 |
| 

`census`

 | 

Required.

Input JSON with details for members to be updated.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The input JSON includes `headers`, which lists the fields to be updated; and `members`, which lists members with their corresponding field-value pairs, including fieldId.

[](https://help.salesforce.com/s?language=en_US)`{     "headers": [         {             "type": "STRING",             "label": "Last Name",             "fieldId": "",             "name": "vlocity_ins__LastName__c"         },         {             "type": "STRING",             "label": "First Name",             "fieldId": "",             "name": "vlocity_ins__FirstName__c"         },         {             "type": "DOUBLE",             "label": "FTE",             "fieldId": "",             "name": "vlocity_ins__FTE__c"         },         {             "type": "PICKLIST",             "label": "Gender",             "fieldId": "",             "name": "vlocity_ins__Gender__c"         },         {             "type": "DATE",             "label": "Birthday",             "fieldId": "",             "name": "vlocity_ins__Birthdate__c"         },         {             "type": "BOOLEAN",             "label": "Is Spouse",             "fieldId": "",             "name": "vlocity_ins__IsSpouse__c"         },         {             "type": "BOOLEAN",             "label": "Primary",             "fieldId": "",             "name": "vlocity_ins__IsPrimaryMember__c"         },         {             "type": "REFERENCE",             "label": "Group Class",             "fieldId": "",             "name": "vlocity_ins__GroupClassId__c"         },         {             "type": "STRING",             "label": "Primary Member Identifier",             "fieldId": "",             "name": "vlocity_ins__PrimaryMemberIdentifier__c"         },         {             "type": "STRING",             "label": "Member Identifier",             "fieldId": "",             "name": "vlocity_ins__MemberIdentifier__c"         },         {             "type": "EMAIL",             "label": "Email",             "fieldId": "",             "name": "vlocity_ins__Email__c"         }     ],     "members": [         {             "vlocity_ins__LastName__c": "Robbins",             "vlocity_ins__FirstName__c": "Timmy",             "vlocity_ins__FTE__c": 1,             "vlocity_ins__Gender__c": "Male",             "vlocity_ins__Birthdate__c": "1985-12-13",             "vlocity_ins__IsSpouse__c": true,             "vlocity_ins__IsPrimaryMember__c": true,             "vlocity_ins__GroupClassId__c": "a3yf4000000LdtrAAC",             "vlocity_ins__MemberIdentifier__c": "1", 	             "vlocity_ins__PrimaryMemberIdentifier__c": null, 	             "vlocity_ins__Email__c": "test@vlocity.com"         },         {             "vlocity_ins__LastName__c": "Robbins",             "vlocity_ins__FirstName__c": "Jason",             "vlocity_ins__FTE__c": 1,             "vlocity_ins__Gender__c": "Male",             "vlocity_ins__Birthdate__c": "1985-10-13",             "vlocity_ins__IsSpouse__c": true,             "vlocity_ins__IsPrimaryMember__c": true,             "vlocity_ins__GroupClassId__c": "a3yf4000000LdtrAAC",             "vlocity_ins__MemberIdentifier__c": "2", 	             "vlocity_ins__PrimaryMemberIdentifier__c": null, 	             "vlocity_ins__Email__c": "test1@vlocity.com"         }     ] }`

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service does not return an output JSON. If any of the entries have errors, those are listed in the output.

[](https://help.salesforce.com/s?language=en_US)`{      "errors":[         {   	      "error":"Birthdate is invalid",             "vlocity_ins__LastName__c": "Robbins",             "vlocity_ins__FirstName__c": "Jason",             "vlocity_ins__FTE__c": 1,             "vlocity_ins__Gender__c": "Male",             "vlocity_ins__Birthdate__c": "1985-10-13",             "vlocity_ins__IsSpouse__c": true,             "vlocity_ins__IsPrimaryMember__c": true,             "vlocity_ins__GroupClassId__c": "a3yf4000000LdtrAAC",             "vlocity_ins__MemberIdentifier__c": "2", 	             "vlocity_ins__PrimaryMemberIdentifier__c": null, 	             "vlocity_ins__Email__c": "test1@vlocity.com"         }    ],    "censusMemberIds":[         "a4C4P000000ed6dUAA"    ] }`

Did this article solve your issue?

Let us know so we can improve!

YesNo