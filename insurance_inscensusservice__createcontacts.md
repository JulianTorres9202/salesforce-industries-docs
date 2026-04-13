---
title: "InsCensusService:createContacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createcontacts.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:createContacts

InsCensusService:createContacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:createContacts

Use this service to create Contacts for census members and community (portal) users.

Important From Winter '23 onward, we have [InsCensusServiceStd:createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createcontacts.htm&language=en_US&type=5 "Use this service to create Contacts for census members.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `createContacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

-   The service uses the `censusId` to retrieve all related `GroupCensusMember__c` records to create a Contact. If a list of `censusMemberIds` is supplied, Contacts will be created for each member. 
    
-   `censusId` takes precedence and ignores `censusMemberIds` if both are used as an input.
    
-   If the `GroupCensusMember__c` already has a linked Contact the service will skip it.
    
-   The service creates the Contact and links it into the `GroupCensusMember__c` record.
    
-   For each `GroupCensusMember__c` the service will check `isPortalUser__c` field. If the field is set to `true`, the service will create a user if the user is not yet existing in the org (based on user email); otherwise it will be skipped. 
    
-   The user is created using the required parameters: `emailEncoding`, `profileId`, `timeZoneSID`, `localeSID`, and `languageLocale`.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`censusId`

 | 

Required.

Id of census used to create Contacts.

 |
| 

`censusMemberIds`

 | 

Required.

List of census member Ids to create Contacts.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`languageLocale`

 | 

Required.

The local language of user.

Example: `en_US`

 |
| 

`localeSID` 

 | 

Required.

Location SID of the user.

Example: `en_US`

 |
| 

`emailEncoding`

 | 

Email encoding type.

Example: `UTF-8`

 |
| 

`profileId`

 | 

Required.

Profile Id of the users to be created

Profile Id is same as User Id.

For more info, refer to [Find the Salesforce ID for a User or profile](https://help.salesforce.com/s/articleView?id=sf.000312782&amp%3Blanguage=en_us&amp%3Btype=1&amp%3Bmode=1&language=en_US&type=5) .

 |
| 

`timeZoneSID`

 | 

Time zone SID of user.

Example: `America/New_York`

 |
| 

`duplicateKeys`

 | 

Comma-delimited field names.

Used to check for duplicate fields.

Example: `FirstName`, `LastName`, `BirthDate`

If not used, duplicate fields are ignored

NOTE: For custom fields, format is namespace followed by field name. For example: `vlocity_ins__Gender__c`

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

There is no input JSON required for this service.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON result will be a list of contact Ids of successfully created census members.

```
{
  "contactIds": [
    "0031U00000pCm53QAC",
    "0031U00000pCm54QAC"
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo