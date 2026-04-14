---
title: "InsQuoteService:removeCoverage"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__removecoverage.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:removeCoverage

InsQuoteService:removeCoverage[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:removeCoverage

Use this service in an OmniScript to remove a specified coverage, as per the product code, from the quote. You can use this service on multiple plans.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

This service isn't supported for guest users.

If a guest user tries to run an OmniScript or Integration Procedure or UI function that uses this service, the service will not run and the guest user will see an error message.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

Method: `removeCoverage`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `quoteId` and product code of a product.
    
2.  Removes all the quote line items for coverages that match the coverages defined by the product codes.
    

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

Id of target quote

 |
| 

`coverageProductCodes`

 | 

Product Code of target coverage.

Takes in a stringified list of product codes, such as Code1,Code2,Code3, and removes all of coverages specified by the product codes.

 |
| 

`planIds`

 | 

Optional.

Ids of target plans, used to target specific plans on the target quote.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON returns a `numCoveragesRemoved` node, which indicates how many coverages were removed:

```
	{'numCoveragesRemoved': 4}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo