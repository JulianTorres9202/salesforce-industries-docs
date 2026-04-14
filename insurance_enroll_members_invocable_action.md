---
title: "Enroll Members Invocable Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_enroll_members_invocable_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Enroll Members Invocable Action

Enroll Members Invocable Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Enroll Members Invocable Action

Creates insurance policies for specified primary members and their dependents by enrolling them into subscribed plans.

This action is available in API version 59.0 and later.

## Supported REST HTTP Methods

**URI**

`/services/data/vXX.X/actions/standard/enrollMembers`

**Formats**

JSON

**HTTP Methods**

GET, POST

**Authentication**

`Authorization: Bearer token`

## Inputs

| Input | Details |
| --- | --- |
| `contractGroupPlanId` | 
**Type**

String

**Description**

Optional. The ID of the contract group plan used to get product and coverage details.

 |
| `contractId` | 

**Type**

String

**Description**

Optional. The ID of the contract record that contains the available plans for group census members.

 |
| `fscNamespace` | 

**Type**

String

**Description**

The namespace of the FSC package.

 |
| `groupCensusMembers` | 

**Type**

List

**Description**

A collection of group census member records to be enrolled.

 |
| `insNameSpace` | 

**Type**

String

**Description**

The namespace of the Insurance package.

 |
| `insuranceRatingRequestId` | 

**Type**

String

**Description**

The ID of the insurance rating request record used to retrieve the insurance rating output record for the specified product and group census members.

 |
| `isNewHire` | 

**Type**

Boolean

**Description**

Optional. A Boolean value that indicates whether the enrollment is for a new hire employee.

 |
| `isSaveMemberPremium` | 

**Type**

Boolean

**Description**

Optional. A Boolean value that indicates whether both total premium and member premium data is captured for a subscriber with dependents. The default value is false and only total premium data is captured.

 |
| `productId` | 

**Type**

String

**Description**

The ID of the plan record to enroll the group census members in.

 |

## Outputs

| Output | Details |
| --- | --- |
| `insurancePolicyIds` | 
**Description**

A collection of the insurance policy record IDs created by the action.

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