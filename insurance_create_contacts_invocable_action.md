---
title: "Create Contacts Invocable Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_contacts_invocable_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Contacts Invocable Action

Create Contacts Invocable Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Contacts Invocable Action

Creates contact records for group census members.

Tip To prevent the creation of duplicate records, use the matchingKeysList input.

This action is available in API version 59.0 and later.

## Supported REST HTTP Methods

**URI**

`/services/data/vXX.X/actions/standard/creaContactsFromGrpCensMembers`

**Formats**

JSON

**HTTP Methods**

GET, POST

**Authentication**

`Authorization: Bearer token`

## Inputs

| Input | Details |
| --- | --- |
| `genderFieldName` | 
**Type**

Text

**Description**

The full name of the Gender field to use to create the contact records, including the namespace. For example, vlocity\_ins\_\_Gender\_\_c.

 |
| `groupCensusMembers` | 

**Type**

Collection

**Description**

A collection of group census member records to create contacts for.

 |
| `matchingKeysList` | 

**Type**

Text

**Description**

A comma-delimited list of Contact object fields to use to detect duplicate account records. If an existing record has matching keys, the action skips the creation of a new record

 |

## Outputs

| Output | Details |
| --- | --- |
| `contactIds` | 
**Description**

A collection of IDs of contact records created by the action.

 |

## Usage

Sample Request

```json
{
  "groupCensusMembers": [
    {"Id": "0r6xx00000003dpAAA"},
    {"Id": "0r6xx00000003fRAAQ"}
  ],
  "matchingKeysList": "FirstName,LastName,Email",
  "genderFieldName": "vlocity_ins__Gender__c"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo