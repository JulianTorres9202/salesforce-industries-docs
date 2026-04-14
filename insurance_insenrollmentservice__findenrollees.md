---
title: "InsEnrollmentService:findEnrollees"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__findenrollees.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService:findEnrollees

InsEnrollmentService:findEnrollees[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService:findEnrollees

Use this service to allow a user to search for a list of enrolled clients.

[](https://help.salesforce.com/s?language=en_US)

Class:`InsEnrollmentService`

Method:`findEnrollees`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service receives the parsed JSON.
    
2.  If the parsed object has a searchKey parameter, it retrieves a list for Contacts with First Name, Last Name, or Member ID that starts with the given searchKey.
    
    -   By default, the service does not return contacts with expired policies.
        
    -   If the parsed object has a productType parameter, the list of Contacts retrieved are filtered further by policy product type.
        
    -   If the parsed object has an includeExpiredPolicies parameter, Contacts are retrieved regardless of their policy’s expiry date
        
3.  The service retrieves a list of policies and maps them to each contact retrieved, as long as their group is the given account id.
    
    -   If the input contains an effectiveDate, only policies with the same effective date are retrieved.
        
    -   If the input contains a productType, only policies with the same productType are retrieved.
        
    -   If the input sets includeExpiredPolicies to true, even expired policies are retrieved.
        
4.  The retrieved enrollee list with all assigned policy details is returned in the data node.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`searchKey`

 | 

Optional

String

Used to check FirstName, LastName, or MemberId of the contacts

 |
| 

`productType`

 | 

Optional

String

Product type used to filter the list of members by their policies’ types

 |
| 

`includeExpiredPolicies`

 | 

Optional

Boolean

Used to determine if the service should include contacts with expired policies

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

JSON input formatted as follows:

```json
{
  "searchKey": String,
  "productType": productType,
  "includeExpiredPolicies": Boolean
}
```

Sample JSON input with data:

```json
{
    "searchKey": "Adam",
    "productType": "Medical",
    "includeExpiredPolicies": true
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The JSON output is a list of enrollees, with the following properties under the `fields` node:

```json
{
  "data": {
    "records": [
      {
        "fields": {
          "Id": "0035w000039SsoSAAS",
		  "AccountId": "0015w00002ADHiPAAX",
          "LastName": "C2P1",
          "FirstName": "P1",
		  "Name": "C2P1 P1"
        }
      }
    ]
  }
}
```

Sample JSON output with data:

```json
{
  "data": [
    {
      "AccountId": "0013h00000Gx5UqAAJ",
      "Id": "0033h00000BBybMAAT",
      "LastName": "C1P1",
      "FirstName": "D1",
      "Name": "D1 C1P1"
    },
    {
      "AccountId": "0013h00000Gx5UqAAJ",
      "Id": "0033h00000BBybPAAT",
      "LastName": "C1P2",
      "FirstName": "D1",
      "Name": "D1 C1P2"
    },
    {
      "AccountId": "0013h00000Gx5UrAAJ",
      "Id": "0033h00000BBybSAAT",
      "LastName": "C2P1",
      "FirstName": "D1",
      "Name": "D1 C2P1"
    }
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo