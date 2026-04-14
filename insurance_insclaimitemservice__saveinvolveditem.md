---
title: "InsClaimItemService:saveInvolvedItem"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__saveinvolveditem.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:saveInvolvedItem

InsClaimItemService:saveInvolvedItem[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:saveInvolvedItem

Use this service to update the total reserve amount of an involved property or involved injury record.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `saveInvolvedItem`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `claimantId` and finds the record of the involved injury or involved property.
    
2.  if the total reserve amount is less than the allocated reserve amount, sets the total reserve amount to equal the allocated reserve amount.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`claimantId`

 | 

Required.

The Id of the involved injury or involved property for which this service will update the total reserve amount.

 |
| 

`totalReserveAmount`

 | 

Required.

The total reserve amount that the service will compare to the allocated reserve amount.

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