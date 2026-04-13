---
title: "InsCensusServiceStd:createContacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createcontacts.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusServiceStd:createContacts

InsCensusServiceStd:createContacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:createContacts

Use this service to create Contacts for census members.

Class: ​`InsCensusServiceStd`​​

Method: `createContacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service uses the ​​`censusMemberIds`​​ to retrieve all related ​`GroupCensusMember​​` records that don't have a Contact record associated with them. ​ ​ ​
2.  If the ​​`GroupCensusMember​​` has a linked Contact, the service skips it. ​ ​ ​
3.  The service creates the Contact and links it into the ​​`GroupCensusMember​​` record.
4.  ​ ​ ​ The service uses the `duplicateKeys` option to identify duplicates. If there is an existing Contact record with the same values for these fields, the service uses the existing Contact record. When there is no `duplicateKeys` parameter in the input, the service creates a new Contact record for each census member. ​ ​ ​
5.  For each ​​`GroupCensusMember​​` the service checks ​`isPortalUser__c`​ field. If its value is ​true​​, the service creates a user if it is doesn't exist in the org (based on user email). ​
6.  The service creates the user based on these required parameters: ​`emailEncoding`​​, ​`profileId`​​, `​timeZoneSID​​`, ​`localeSID`​​, and `​languageLocale`​​.

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`censusMemberIds`

 | 

Required.

List of group census member Ids to create Contacts.

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

The local language of the user.

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

Profile Id is the same as User Id.

For more info, refer to [Find the Salesforce ID for a User or profile](https://help.salesforce.com/s/articleView?id=000312782&language=en_US&type=1) .

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

Comma-delimited field names to check for duplicate fields.

Example: `FirstName`, `LastName`, `BirthDate`

If not used, the service ignores all duplicate fields.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

There is no input JSON required for this service.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a list of contact Ids of successfully created census members.

Ids of `GroupCensusMember` records

```
{      
    "censusMemberIds": [
        "0r6RO0000000430YAA",
        "0r6RO000000042vYAA"
    ],
    "duplicateKeys": "FirstName,LastName"
    "emailEncoding": "UTF-8",
    "timeZoneSID": "America/New York",
    "languageLocale": "en_US",
    "localeSID": "en_US",
    "profileId": "00eRO000000OUVRYA4",
}
```

Ids of `Contact` records

```
{    
    "contactIds": [
        "003RO000002yi8iYAA",
        "003RO000002yi8dYAA"
    ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo