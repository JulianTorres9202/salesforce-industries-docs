---
title: "Create Portal Users Invocable Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_portal_users_invocable_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Portal Users Invocable Action

Create Portal Users Invocable Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Portal Users Invocable Action

Creates user records with the IsPortalUser property enabled for group census members.

This action is available in API version 59.0 and later.

## Supported REST HTTP Methods

**URI**

`/services/data/vXX.X/actions/standard/creaUsersFromGrpCensusMembers`

**Formats**

JSON

**HTTP Methods**

GET, POST

**Authentication**

`Authorization: Bearer token`

## Inputs

| Input | Details |
| --- | --- |
| `emailEncodingKey` | 
**Type**

Text

**Description**

The email encoding key to use to create the user records. For example, `ISO-8859-1` or `UTF-8`.

 |
| `groupCensusMembers` | 

**Type**

Collection

**Description**

A collection of group census member records to create user records for.

 |
| `languageLocaleKey` | 

**Type**

Text

**Description**

The language to use to create the user records. For example fr for French or zh\_Cw for Chinese (Traditional).

 |
| `localeSidKey` | 

**Type**

Text

**Description**

The SID key of the locale to use to create user records.

 |
| `profileId` | 

**Type**

Text

**Description**

The ID of the profile to use to create the user records.

 |
| `timeZoneSidKey` | 

**Type**

Text

**Description**

The time zone SID key to use to create the user records.

 |

## Outputs

| Output | Details |
| --- | --- |
| `userIds` | 
**Description**

A collection of user IDs created by the action.

 |

## Usage

Sample Request

```json
{
  "groupCensusMembers": [
    {"Id": "0r6xx00000003dpAAA"},
    {"Id": "0r6xx00000003fRAAQ"}
  ],
  "profileId": "00exx000000mzzxAAA",
  "timezoneSidKey": "America/New_York",
  "emailEncodingKey": "UTF-8",
  "localeSidKey": "en_US",
  "languageLocaleKey": "en_US"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo