---
title: "InsClaimItemService:getInvolvedItems"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__getinvolveditems.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:getInvolvedItems

InsClaimItemService:getInvolvedItems[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:getInvolvedItems

Use this service to get a list of involved items (property) and/or involved people (parties) for a specific claim.

Note

The involved items and involved people this service returns are also called claimants.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `getInvolvedItems`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `claimId` and gets the claim record.
    
2.  Returns a list of claimants, including both involved property and involved people, associated with the claim.
    
3.  If `includeCoverages` is set to `true`, the service includes a list of all coverages associated with each claimant.
    
    For third-party claimants (property or people who are not covered by the in-force insurance policy), the service returns coverages that are associated with the peril product.
    

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

The Id of the claim this service will get insured items for.

 |
| 

`includeCoverages`

 | 

Optional.

`True` or `false`.

If set to `true`, includes coverages for each involved injury and involved property in the list this service returns.

If set to `false`, the output JSON does not include the list of `options` attributes.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a JSON-formatted list of claimants (insured items and insured people).

```
claimants = [
    { 
        "Id": "01t000000000000000", 
        "Name": "Bodily Injury", 
        "Description": "",
        "options": [
            { ... },
            { ... },
            { ... }
        ]
    }, 
    { ... }
];
```

[](https://help.salesforce.com/s?language=en_US)

## Examples

The service is typically used in claims flows to get a list of claimants (involved items and involved people).

Did this article solve your issue?

Let us know so we can improve!

YesNo