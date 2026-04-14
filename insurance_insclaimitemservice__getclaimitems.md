---
title: "InsClaimItemService:getClaimItems"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getclaimitems.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:getClaimItems

InsClaimItemService:getClaimItems[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:getClaimItems

Use this service to retrieve the list of Claimants and their corresponding open ClaimCoverages with the respective line items (loss or expense).

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `getClaimItems`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `claimId` and gets all the open coverages and their line items (if any).
    
2.  Finds the claim line items of the specified type.
    
3.  Returns a JSON of loss claim line items, grouped under involved items and involved parties. This JSON includes coverage amounts and adjusted amounts for each involved item, involved party, and coverage associated with each of these.
    
    For expense type, returns a JSON including the details of each expense claim line item.
    
    Note
    
    This service now uses the interface fields that are common between the Vlocity Data Model and the Salesforce Data Model.
    
    You can use this service to get both Loss claim line items or Expense claim line items, but not both types at the same time.
    

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

The Id of the claim for which the service gets claim line items.

 |
| 

`type`

 | 

Optional.

`Loss` or `Expense` are valid values.

If no value is entered, the service defaults to `Loss`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```
{ 
	"claimId": <Id>,
	"type": <String>
}
```

Here's an example of the input JSON:

```
{ 
	"claimId": "01t000000000000001",
	"type": "Loss"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a JSON that contains the claim items or expense items, depending on the claim type. Here's the format of the output JSON:

```
{  
   	"claimItems": [
		{
			"coverages" : [
                 "claimItems" : []
            ]
		}
	]
}

// or 

{  
   	"expenseItems": [
		{
			"coverages" : [
                 "expenseItems" : []
            ]
		}
	]
}
```

Here's an example of the output JSON:

```
// sample of 2 Claimants, 1 with 2 open coverages (Collision, and BIPD with 1 loss item), the other with 1 open coverage (Collision with 1 loss item).

{
  "claimItems": [
    {
      "coverages": [
        {
          "claimItems": [
            {
              "currencyIsoCode": "USD",
              "additionalInfo": {},
              "adjustedAmount": 200,
              "claimAmount": 200,
              "claimCoverageId": "0kP5e000000wk8DEAQ",
              "claimId": "0Zk5e0000010xPlCAI",
              "createdDate": "2021-07-28T18:39:36.000Z",
              "currencySymbol": "$",
              "description": "checkup for whiplash",
              "id": "0l25e000000sXzLAAU",
              "name": "Bodily Injury & Property Damage - 1",
              "recipientId": "0aS5e0000010wl7EAA",
              "recipientName": "Joe Black",
              "status": "Open",
              "type": "Loss"
            }
          ],
          "reserveAmount": 3200,
          "reserveStatus": "Open",
          "currencyIsoCode": "USD",
          "currencySymbol": "$",
          "createdDate": "2021-07-28T08:06:26.000Z",
          "coverageName": "Bodily Injury & Property Damage",
          "involvedName": "Excavator",
          "involvedId": "0dq5e0000010wknAAA",
          "insuredName": "Audi A5",
          "insuredId": "0YW5e000000wvVYGAY",
          "coverageStatus": "Open",
          "coverageMode": "CoverageReserve",
          "claimCoverageId": "0kP5e000000wk8DEAQ"
        },
        {
          "claimItems": [],
          "reserveAmount": 1230,
          "reserveStatus": "Open",
          "currencyIsoCode": "USD",
          "currencySymbol": "$",
          "createdDate": "2021-07-28T18:37:59.000Z",
          "coverageName": "Collision",
          "involvedName": "Excavator",
          "involvedId": "0dq5e0000010wknAAA",
          "insuredName": "Audi A5",
          "insuredId": "0YW5e000000wvVYGAY",
          "coverageStatus": "Open",
          "coverageMode": "CoverageReserve",
          "claimCoverageId": "0kP5e000000wk8cEAA"
        }
      ],
      "claimantName": "Joe Black",
      "claimantId": "0aS5e0000010wl7EAA"
    },
    {
      "coverages": [
        {
          "claimItems": [
            {
              "childClaimItems": [
                {
                  "adjustedAmount": 100,
                  "adjustmentReason": "Deductible",
                  "currencyIsoCode": null,
                  "currencySymbol": null,
                  "id": null,
                  "name": null,
                  "parentLineItemId": "0l25e000000sXzGAAU"
                }
              ],
              "currencyIsoCode": "USD",
              "additionalInfo": {},
              "adjustedAmount": 0,
              "claimAmount": 100,
              "claimCoverageId": "0kP5e000000wk8EEAQ",
              "claimId": "0Zk5e0000010xPlCAI",
              "createdDate": "2021-07-28T18:37:01.000Z",
              "currencySymbol": "$",
              "description": "repair tail light",
              "id": "0l25e000000sXzGAAU",
              "name": "Collision - 1",
              "recipientId": "0aS5e0000010wl2EAA",
              "recipientName": "Ernie Newton",
              "status": "Open",
              "type": "Loss"
            }
          ],
          "reserveAmount": 3200,
          "reserveStatus": "Open",
          "currencyIsoCode": "USD",
          "currencySymbol": "$",
          "createdDate": "2021-07-28T08:06:27.000Z",
          "coverageName": "Collision",
          "involvedName": "Audi A5",
          "involvedId": "0dq5e0000010wkiAAA",
          "insuredName": "Audi A5",
          "insuredId": "0YW5e000000wvVYGAY",
          "coverageStatus": "Open",
          "coverageMode": "CoverageReserve",
          "claimCoverageId": "0kP5e000000wk8EEAQ"
        }
      ],
      "claimantName": "Ernie Newton",
      "claimantId": "0aS5e0000010wl2EAA"
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo