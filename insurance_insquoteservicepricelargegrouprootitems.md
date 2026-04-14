---
title: "InsQuoteService:priceLargeGroupRootItems"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservicepricelargegrouprootitems.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:priceLargeGroupRootItems

InsQuoteService:priceLargeGroupRootItems[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:priceLargeGroupRootItems

This service calculates the price, and optionally taxes and fees, for a specific root item or all root items for a large group quote.

Class: `InsQuoteService`

Method: `priceLargeGroupRootItems`

## How It Works

1.  The service takes a Quote ID as a required input. When the `isRateAll` option is set to `false`, a Quote Line Item ID of the root Quote Line Item to be priced is also required.
2.  The service queries the target Quote to make sure there is a Group Census associated with the Quote.
3.  The service determines if the product or products are configured for Member Based or Summary Based rating.
    1.  If `isRateAll` is set to `true`, the service queries all the root items under the Quote. It looks at the product associated with each Quote Line Item and, based on the `PricingStrategyType__c` option, determines if the Product is configured for Member Based or Summary Based rating. Then the service splits the Quote Line Items into two groups.
    2.  If `isRateAll` is set to `false`, the service queries the target root item and determines if the product associated with the Quote Line Item is configured for Member Based Rating or Summary Based Rating.
4.  If there are root items configured for Member Based rating, the service calls the `InsuranceRatingPtc.rateCensus` service to calculate a price for all the root items configured for Census Based Rating in a single batch. The `InsuranceRatingPtc.rateCensus` service is an async service so it doesn't update the price for these root items. Instead, it returns an async request ID and batch Job ID.
5.  If there are root items configured for Summary Based Rating, the service calls the `InsuranceRatingPtc.rateCensusSummary` service to calculate a price for all the root items configured for Summary Based Rating in a single batch. The `InsuranceRatingPtc.rateCensusSummary` service is a synchronous service, so the service updates the price for these root items synchronously.
6.  The service returns the ID list of root items configured for Census Based Rating and the ID list of root items configured for Summary Based Rating. The service returns an optional `asyncRequestId` and `batchJobId` if there are root items configured for Census Based Rating.

## Inputs

| Input | Description |
| --- | --- |
| `jurisdiction` | 
Optional.

The jurisdiction used to qualify census members.

 |
| `quoteId` | 

Required.

The ID of the quote.

 |
| `rootLineId` | 

Required when the `isRateAll` option is `false`.

The ID of the root line item.

 |

## Remote Options

| Option | Description |
| --- | --- |
| `calculateTaxesAndFees` | 
Optional.

Default value is `true`.

Set to `true` to calculate taxes and fees.

 |
| `effectiveDate` | 

Required.

The effective date used for rating.

 |
| `isRateAll` | 

Required.

Boolean.

Default value is `false`.

Indicates whether to rate all root items in the quote.

 |

## Input JSON

Here's the sample input JSON:

```json
{
  "quoteId": "0Q05w000001mgQNCAY",
  "rootLineId": "0QL5w000003kyBnGAI"
}
```

## Options JSON

Here's the sample options JSON:

```json
{     
  "isRateAll": false,
  "effectiveDate": "2023-06-22",
  "calculateTaxesAndFees": true 
}
```

## Output JSON

Here's the sample output JSON:

```json
{
  "hasAsyncCall": true,
  "summaryRatingLineIds": {"0QL5w000003kyBnGAI"},
  "asyncRatingLineIds": {"0QL5w0000044u0SGAQ"},
  "asyncRequestId": "8zk9f00000Q5jUEHNS",
  "batchJobId": "0md9f00000Q5jUEHNS",
  "calculatedTaxesAndFees": {
    "0QL5w0000044u0UGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0SGAQ": {
      "feeAmount": null,
      "taxAmount": null
    }
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo