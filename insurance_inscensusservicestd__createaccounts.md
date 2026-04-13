---
title: "InsCensusServiceStd:createUpdateAccounts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createaccounts.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusServiceStd:createUpdateAccounts

InsCensusServiceStd:createUpdateAccounts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:createUpdateAccounts

Use this service to create Person Accounts for the members in the given census. It also updates the existing person accounts using the `duplicateKeys` parameter.

Class: `InsCensusServiceStd`

Method: `createUpdateAccounts`

Note

Person Accounts must be enabled in the org when using this service.

[](https://help.salesforce.com/s?language=en_US)

## How it Works

To create person accounts for the members in the given census, this service:

1.  Retrieves the list of ​`GroupCensusMember​​` records based on `censusMemberIds​.`
2.  Creates a Person Account for each ​`GroupCensusMember`​​.
3.  The following four fields, along with mapping are copied from `GroupCensusMember` to the Account record.
    
    | GroupCensusMember | Account |
    | --- | --- |
    | FirstName | FirstName |
    | Lastname | LastName |
    | Email | PersonEmail |
    | Birthdate | PersonBirthdate |
    
4.  If you provide `duplicateKeys` parameter in the input, the service uses the list of comma-separated fields of Account object for identifying the duplicate records. If there is an existing Account record with the same values for these fields, then the service uses the existing Account record. If there is no `duplicateKeys` parameter, the service creates a new Account record for each census member.
    
    1.  The fields passed in `duplicateKeys` must be a subset of the fields that are copied to the Account record. If you pass any other fields, they're ignored during duplicate detection.
        
5.  Updates the ​`AccountId`​ and ​`ContactId`​​ fields of the census member.
    
6.  Sets ​`GroupCensusMember.AccountId`​ as the ID of the newly created Person Account and ​`GroupCensusMember.ContactId​​` as the corresponding Contact record.
    
7.  The service creates a user record for the `GroupCensusMember` records whose `IsPortalUser` is true. It uses `emailEncoding`, `localeSID`, `languageLocale`, `timeZoneSID` and `profileId` fields to create a User record.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| Option​ | ​Description​ |
| --- | --- |
| ​​​`censusMemberIds`​​​ | 
​Required.​

List of `GroupCensusMember` record Ids for which Account records are created. ​

 |
| `​​​duplicateKeys​​​` | 

A string of comma-separated fields of Account object for checking duplicate against existing Account records. ​Example: `FirstName`, `LastName`, `BirthDate`​. If you don't use this option, all the duplicate fields are ignored.​

 |
| ​​​`personAccountRecordType​​​` | 

​Optional.​

The record type of the person account.​​ If the value isn't passed, it defaults to Person Account.

 |
| ​​​`emailEncoding​​​` | 

​Required.​

The encoding format for creating a user record.​

 |
| `​​​localeSID`​​​ | 

​Required.​

The security identifier of the geographical location.​

 |
| `​​​languageLocale`​​​ | 

Required. ​

The security identifier of the language.​

 |
| `​timeZoneSID​` | 

Required.​

The security identifier of the time zone.​

 |
| ​`profileId​` | 

Required.​

The ID of the profile record that is associated with the user record.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

There’s no input JSON required for this service.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON is a list of account Ids of successfully created or update `GroupCensusMember` records.

Ids of `GroupCensusMember` records:

```json
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

Ids of `Contact` records:

```json
{    
    "accountIds": [
        "003RO000002yi8iYAA",
        "003RO000002yi8dYAA"
    ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo