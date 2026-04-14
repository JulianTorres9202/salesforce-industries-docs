---
title: "InsClaimItemService:getPartyContacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getpartycontacts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:getPartyContacts

InsClaimItemService:getPartyContacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:getPartyContacts

Use this service to get a list of all the contact information for all involved parties in a specified claim.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `getPartyContacts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `claimId` and gets the claim record.
    
2.  Returns a list of all the contact info for all involved parties in this claim.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`claimId`

 | 

Required.

The Id of the claim for which this service will get contact information for involved parties.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a JSON formatted list of contact information for all the involved parties for the specified claim.

```
"partyContacts": [
    {
      "Address": {
        "city": "San Francisco",
        "country": USA,
        "geocodeAccuracy": null,
        "latitude": null,
        "longitude": null,
        "postalCode": "94103",
        "state": "CA",
        "street": "50 Fremont"
      },
      "Phone": "555 123 4567",
      "Email": marysue@mailinator.com,
      "Name": "Mary Sue Smith",
      "RelationshipType": "Payee",
      "Id": "a461U00000064BEQAY"
    },
    {
      "Address": null,
      "Phone": 555 765 1212,
      "Email": john.doe@mailinator.com,
      "Name": "John Doe",
      "RelationshipType": "Witness",
      "Id": "a461U00000065RWQAY"
    },
    {
      "Address": {
        "city": "Mountain View",
        "country": USA,
        "geocodeAccuracy": null,
        "latitude": null,
        "longitude": null,
        "postalCode": 94043,
        "state": "CA",
        "street": 1000 Castro St
      },
      "Phone": "123 456 7890",
      "Email": "joansmith42@mailinator.com",
      "Name": "Joan Smith",
      "RelationshipType": "Payee",
      "Id": "a461U0000005xS0QAI"
    }
  ],    
```    

Did this article solve your issue?

Let us know so we can improve!

YesNo