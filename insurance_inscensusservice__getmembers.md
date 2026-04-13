---
title: "InsCensusService:getMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__getmembers.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:getMembers

InsCensusService:getMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:getMembers

Use this service to retrieve the members of a census. It also retrieves the fields. Guest user access is enabled for this service.

Important From Winter '23 onward, we have [InsCensusServiceStd:getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmembers.htm&language=en_US&type=5 "Use this service to retrieve the members of a census from the GroupCensusMember. It also retrieves the headers based on the fieldsetName.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `getMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service has two key functions:

1.  Retrieve the list of GroupCensusMember\_\_c fields based on a fieldset defined in fieldset Name parameter. The output always contain MemberIdentifier\_\_c, PrimaryMemberIdentifier\_\_c, RelatedCensusMemberId\_\_c, IsPrimaryMember\_\_c and IsSpouse\_\_c even if they are not in the fieldset.
    
2.  Retrieve the `GroupCensusMember__c` records.
    
    [](https://help.salesforce.com/s?language=en_US)
    1.  The service uses a `censusId` to retrieve census members from `GroupCensusMember__c`.
        
    2.  If the offset parameter has value, it retrieves 2000 rows after the offset.
        
    3.  The list of members is placed into the `members` node.
        

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

`fieldsetName`

 | 

Optional

-   If it has a valid value, retrieves `GroupCensusMember__c` fields that is part of the fieldset.
    
-   If the value is not valid, no fields are returned.
    
-   If there is no value, retrieves `GroupCensusMember__c` fields that is part of the default fieldset (EditableTable)
    

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

The service returns an output JSON, formatted as per the example below, with details for the members in the census, where `headers` is a list of valid fields according to the Census Member fieldset `EditableTable` and `members` is a list of members which includes a fieldId for each member.

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
    },
    {
      "type": "REFERENCE",
      "label": "Primary Census Member",
      "fieldId": "",
      "name": "vlocity_ins__RelatedCensusMemberId__c"
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
	       "vlocity_ins__Email__c": "test@vlocity.com",
		"vlocity_ins__RelatedCensusMemberId__c" : null
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
	       "vlocity_ins__PrimaryMemberIdentifier__c":"1",
	       "vlocity_ins__Email__c": "test1@vlocity.com",
		"vlocity_ins__RelatedCensusMemberId__c" : "a3yf4000000MdtrAAC"
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo