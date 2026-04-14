---
title: "Create Accounts Invocable Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_accounts_invocable_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Accounts Invocable Action

Create Accounts Invocable Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Accounts Invocable Action

Create person account records of the specified type for group census members.

Tip To prevent the creation of duplicate records, use the matchingKeysList input.

This action is available in API version 59.0 and later.

Enable person accounts for Carrier Admin or other roles. To learn how to enable person account, see [Enable Person Accounts](https://help.salesforce.com/s/articleView?id=sales.account_person_enable.htm&language=en_US&type=5).

## Supported REST HTTP Methods

**URI**

`services/data/vXX.X/actions/standard/creaPersAccountsFromGrpCensMbr`

**Formats**

JSON

**HTTP Methods**

GET, POST

**Authentication**

`Authorization: Bearer token`

## Inputs

| Input | Details |
| --- | --- |
| `groupCensusMembers` | 
**Type**

Collection

**Description**

A collection of group census member records to create accounts for.

 |
| `matchingKeysList` | 

**Type**

Text

**Description**

A comma-delimited list of Account object fields to use to detect duplicate account records. If an existing record has matching keys, the action skips the creation of a new record.

 |
| `recordTypeName` | 

**Type**

Text

**Description**

The name of the record type to use to create the person accounts.

 |

## Outputs

| Output | Details |
| --- | --- |
| `accountIds` | 
**Description**

A collection of account IDs created by the action.

 |

## Usage

Sample Request

```json
{
  "groupCensusMembers": [
    {"Id": "0r6xx00000003dpAAA"},
    {"Id": "0r6xx00000003fRAAQ"}
  ],
  "matchingKeysList": "FirstName,LastName,PersonEmail",
  "recordTypeName": "SamplePersonAccountType"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo