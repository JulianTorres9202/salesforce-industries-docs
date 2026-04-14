---
title: "InsQuoteService:getPlanSpecs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getplanspecs.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:getPlanSpecs

InsQuoteService:getPlanSpecs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:getPlanSpecs

Use this service to get all the quote line items (that is to say, the plan specs) associated with a specific product.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `getPlanSpecs`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `quoteId` and `productId`.
    
2.  Returns quote line item id, instance key of the quote line item, and product info for any plan using the specified product.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`quoteId`

 | 

Required

Id of target quote.

 |
| 

`productSpecId`

 | 

Id of target Product.

Ignored if `coverageSpecIds` option is provided.

 |
| 

`coverageSpecIds`

 | 

List of Coverage Ids.

Ignored if `productSecId` option is provided.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a list in the output JSON of either QuoteLineItem specs for the product Ids which match the target product Id, or of QuoteLineItem specs which contain a child with a productId that matches any of the provided Coverage Ids (example below).

Note

The fields returned in the output JSON can be updated by modifying the `GetQuoteLineItemSpec` fieldSet on the QuoteLineItem object. Note that the Id, instanceKey, and productId fields will always be returned, even if they are removed from the fieldSet.

```
{
  'records': [{
    'Id': '0QLf4000000SX3tGAG',
    'instanceKey': 'Coverage 1a',
    'productId': '01tf4000001ZcLnAAK'
  }, {
    'Id': '0QLf4000000SX3rGAG',
    'instanceKey': 'Coverage 1b',
    'productId': '01tf4000001ZcLnAAK'
  }]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo