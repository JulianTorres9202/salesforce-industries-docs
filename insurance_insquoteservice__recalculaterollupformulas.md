---
title: "InsQuoteService:recalculateRollupFormulas"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__recalculaterollupformulas.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:recalculateRollupFormulas

InsQuoteService:recalculateRollupFormulas[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:recalculateRollupFormulas

Use this service to sum the price at the child or grandchild quote line item level and recalculates it to the parent quote line item level.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `recalculateRollupFormulas`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service is mainly used for large, multi-instance quotes.

1.  When `[InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.")` is not completed in one call, the quote is updated with a subset of quote line items through multiple calls; hence, the roll-up in each call is not a complete price.
    
2.  This service takes as an input or remote option the `quoteId` of the quote that needs to recalculate the roll-up price.
    
3.  After all quote line items are added to the quote, this service re-calculates the roll-up price at the parent and root quote line item level.
    

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

Id of the quote that the service will use to recalculate the rollup price.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's a simple example of an updated quote line item Id and its unit price: 

```
{
   "0QL1U0000006GZ4WAM": 1283
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo