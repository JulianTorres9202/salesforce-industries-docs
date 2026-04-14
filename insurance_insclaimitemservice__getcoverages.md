---
title: "InsClaimItemService:getCoverages"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getcoverages.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:getCoverages

InsClaimItemService:getCoverages[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:getCoverages

Use this service to get coverages that apply to a specific claim.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getCoverages`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the claimId and gets the claim record.
    
2.  Returns a JSON containing a list of all coverages that apply to the claim.
    

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

The Id of the claim the service the service finds and returns coverages for.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a list of coverages for the specified claim.

```
coverages = [
    { 
        "Id": "01t000000000000000", 
        "Name": "Bodily Injury", 
        "Description": "", 
        "insuredItem": "2016 Camry Toyota", // optional
        "insuredParty": "Primary Driver Person" // optional
    }, 
    { ... }
];    
```    

Did this article solve your issue?

Let us know so we can improve!

YesNo