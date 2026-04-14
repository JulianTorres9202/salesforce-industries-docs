---
title: "InsCensusService:createAccounts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__createaccounts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:createAccounts

InsCensusService:createAccounts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:createAccounts

Use this service to create Person Accounts for the members in the given census.

Important From Winter '23 onward, we have [InsCensusServiceStd:createUpdateAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createaccounts.htm&language=en_US&type=5 "Use this service to create Person Accounts for the members in the given census. It also updates the existing person accounts using the duplicateKeys parameter.") service enabled to work with Salesforce Standard Data Model for Financial Services Cloud and Health Cloud. Existing customers can continue to use this service, but no further enhancements will be provided in the Insurance Managed Package.

Class: `InsCensusService`

Method: `createAccounts`

Note

Person Accounts must be enabled in the org when using this service.

[](https://help.salesforce.com/s?language=en_US)

## How it Works

To create person accounts for the members in the given census, this service:

1.  Uses the `censusId` to retrieve the list of `GroupCensusMember__c` records.
    
2.  Then it creates a Person Account for each `censusMember.`
    
3.  Creates an ACR (AccountContactRelation) record.
    
    Note
    
    ACR.accountId = groupAccountId
    
    ACR.ContactId = PersonContactId of the created Person Account
    
4.  Updates the `AccountId__c` and `ContactId__c` fields of the census member.
    
5.  Sets `GroupCensusMember__c.AccountId__c` as the Id of the newly created Person Account and `GroupCensusMember__c.ContactId__c` as the corresponding `PersonContactId`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`censusId`

 | 

Required.

Id of census to retrieve the group members.

 |
| 

`personAccountRecordType`

 | 

Optional.

Name of the person account record type to be associated with the created person accounts.

Note

If the value isn’t passed, it defaults to "Person Account."







 |
| 

`batchSize`

 | 

Number of records to be processed per batch job.

Note

Supported only for small and medium groups (up to 900 records which includes both primary members and dependents).







 |
| 

`jobSize`

 | 

Number of records to be processed per asynchronous Apex job.

This parameter determines how many apex jobs are instantiated, given the number of records.

Note

Salesforce allows a maximum five apex jobs to run in parallel.







 |
| 

`portalUsersOnly`

 | 

Notifies the community admin to create or configure the community users.

 |
| 

`duplicateKeys`

 | 

Comma-delimited field names. This option checks for duplicate fields.

Example: FirstName, LastName, BirthDate

If this option isn’t used, all the duplicate fields are ignored.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

There’s no input JSON required for this service.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON is a list of account Ids of successfully created Person Accounts.

```json
{  
  "accountIds": [
    "0015e00000JWzpKAAT",
    "0015e00000JWzpLAAT",
    "0015e00000JWzpMAAT"
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo