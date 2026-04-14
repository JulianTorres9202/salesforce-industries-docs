---
title: "InsCensusService:deleteMembers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__deletemembers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:deleteMembers

InsCensusService:deleteMembers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:deleteMembers

Use this service to delete the members from a census.

Important From Winter '23 onward, we have [InsCensusServiceStd:deleteMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletemembers.htm&language=en_US&type=5 "Use this service to delete the group census members.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `deleteMembers`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

-   The service takes the members in an input JSON and deletes them from the given census Id.
    
-   Works for both `getMembers` and `getMembersWithPlans` in an OmniScript.
    
-   Guest user access is enabled for this service.
    

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

ID of the census with members to delete.

 |
| 

`census`

 | 

Required.

Input JSON of the members to be deleted.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The input JSON includes `headers`, which lists the Group Census Member fields, and the list of members that must be deleted. Id field is the required field for both headers and members.

```
{
    "headers": [
        {
            "type": "STRING",
            "label": "Id",
            "fieldId": "",
            "name": "Id"
        }
    ],
    "members": [
        {
            "Id": "12345678"
        },
        {
            "Id": "12345679"
        },
        {
            "Id": "12345677"
        }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service does not return an output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo