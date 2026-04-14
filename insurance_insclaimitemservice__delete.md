---
title: "InsClaimItemService:delete"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__delete.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:delete

InsClaimItemService:delete[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:delete

Use this service to delete a claim line item from a claim object.

Works for both Loss and Expense type claim line items.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `delete`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `claimItemId` and finds the record of the claim line item.
    
2.  Deletes the specified claim line item from the claim object.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`claimItemId`

 | 

Required.

The Id of the claim line item this service will delete.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service does not return an output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo