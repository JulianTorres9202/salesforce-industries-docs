---
title: "InsEnrollmentService: getEnrolleePolicies"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__getenrolleepolicies.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService: getEnrolleePolicies

InsEnrollmentService: getEnrolleePolicies[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService: getEnrolleePolicies

Use this service to allow a user to search for the policies of a given set of enrolled clients.

[](https://help.salesforce.com/s?language=en_US)

Class:`InsEnrollmentService`

Method:`getEnrolleePolicies`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service receives the parsed JSON.
    
    -   If the input does not contain an accountId, an error is returned.
        
    -   If the input does not contain a valid list of contact ids, an error is returned.
        
2.  The service retrieves a list of contacts for each contactId.
    
3.  The service retrieves a list of policies and map them to each contact retrieved, as long as their group is the given account id.
    
    -   If the input contains an effectiveDate, only policies with the same effective date are retrieved.
        
    -   If the input contains a productType, only policies with the same productType are retrieved.
        
    -   If the input sets includeExpiredPolicies to true, even expired policies are retrieved.
        
4.  The Product details for retrieved policies are also retrieved, including the list of dependents registered for a given policy.
    
5.  The retrieved enrollee list with all assigned policy details is returned in the `data` node.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`contactIds`

 | 

List of contact Ids who own the assets to be retrieved.

 |
| 

`accountId`

 | 

Id of the account used to filter retrieved enrollments.

 |
| 

`effectiveDate`

 | 

Optional

String

Date string used to filter the list of retrieved enrollments based on when the Policy came into effect.

 |
| 

`productType`

 | 

Optional

String

Filters the list of retrieved enrollments based on the product type.

 |
| 

`includeExpiredPolicies`

 | 

Optional

Boolean

Determines if the service should include contacts with expired policies

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

JSON format:

```json
{
  "contactIds": [ContactId],
  "accountId": accountId,
  "effectiveDate": Date,
  "productType": productType,
  "includeExpiredPolicies": Boolean
}
```

Sample data output:

```json
{
    "contactIds": [ "0035w000034kiVwAAI" ],
    "accountId": "0015w00002ADHiPAAX",
    "effectiveDate": "6/12/2020",
    "productType": "Medical",
    "includeExpiredPolicies": true
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

JSON format:

```json
{
  "data": [
    {
      "enrollments": [
        {
          "dependents": [
            {
              "partyId":Id,
              "contactId": Id,
              "relationshipType": String,
              "LastName": String",
              "FirstName": String,
              "Id": Id
            }
          ],
          "EffectiveEnd": Date,
          "EffectiveStart": Date,
          "Name": String,
          "productName": String,
          "primaryMemberContactId": Id,
          "policyNumber": String,
          "accountId": Id,
          "productId": Id,
          "Id": Id
        }
      ],
      "AccountId": Id,
      "Id": Id,
      "LastName": String,
      "FirstName": String,
      "Name": String
    }
  ],
  "error": "OK"
}
```

Sample data output:

```json
{
  "data": [
    {
      "enrollments": [
        {
          "dependents": [
            {
              "partyId": "a0z3h0000036sJiAAI",
              "contactId": "0033h00000BBybMAAT",
              "relationshipType": "Dependent",
              "LastName": "C1P1",
              "FirstName": "D1",
              "Id": "a4B3h000000IdiMEAS"
            },
            {
              "partyId": "a0z3h0000036sJjAAI",
              "contactId": "0033h00000BBybNAAT",
              "relationshipType": "Dependent",
              "LastName": "C1P1",
              "FirstName": "D2",
              "Id": "a4B3h000000IdiNEAS"
            }
          ],
          "EffectiveEnd": null,
          "EffectiveStart": "2020-06-12",
          "Name": "Policy1",
          "productName": "MedPlan A",
          "primaryMemberContactId": "0033h00000BBybLAAT",
          "policyNumber": null,
          "accountId": "0013h00000Gx5UqAAJ",
          "productId": "01t3h000002T4JmAAK",
          "Id": "02i3h00000037xxAAA"
        }
      ],
      "AccountId": "0013h00000Gx5UqAAJ",
      "Id": "0033h00000BBybLAAT",
      "LastName": "C1P1",
      "FirstName": "P1",
      "Name": "P1 C1P1"
    },
    {
      "enrollments": [
        {
          "dependents": [
            {
              "partyId": "a0z3h0000036sJlAAI",
              "contactId": "0033h00000BBybPAAT",
              "relationshipType": "Dependent",
              "LastName": "C1P2",
              "FirstName": "D1",
              "Id": "a4B3h000000IdiOEAS"
            },
            {
              "partyId": "a0z3h0000036sJmAAI",
              "contactId": "0033h00000BBybQAAT",
              "relationshipType": "Dependent",
              "LastName": "C1P2",
              "FirstName": "D2",
              "Id": "a4B3h000000IdiPEAS"
            }
          ],
          "EffectiveEnd": null,
          "EffectiveStart": "2020-06-12",
          "Name": "Policy2",
          "productName": null,
          "primaryMemberContactId": "0033h00000BBybOAAT",
          "policyNumber": null,
          "accountId": "0013h00000Gx5UqAAJ",
          "productId": null,
          "Id": "02i3h00000037xyAAA"
        }
      ],
      "AccountId": "0013h00000Gx5UqAAJ",
      "Id": "0033h00000BBybOAAT",
      "LastName": "C1P2",
      "FirstName": "P2",
      "Name": "P2 C1P2"
    }
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo