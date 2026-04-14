---
title: "InsQuoteService:priceRootItem"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__pricerootitem.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:priceRootItem

InsQuoteService:priceRootItem[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:priceRootItem

Use this service to calculate the price (and optionally, taxes and fees) for a target root item and its children under a Quote.

[](https://help.salesforce.com/s?language=en_US)

Class: InsQuoteService

Method: priceRootItem

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  This service takes in a Quote ID as well as the QuoteLineItem ID of the root QuoteLineItem to price.
    
2.  The service will then look at the Product associated with the target QuoteLineItem and run the Calculation Procedure/Integration Procedure for that Product in order to calculate the Price.
    
    [](https://help.salesforce.com/s?language=en_US)
    -   If also calculating taxes and fees, all taxes and fees assigned to the associated Product are also executed.
        
3.  The calculated Price is then persisted onto the target QuoteLineItem and returned in the output.
    
    [](https://help.salesforce.com/s?language=en_US)
    -   If also calculating taxes and fees, the taxes and fees are also persisted on the target QuoteLineItem and returned in the output.
        

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

Required.

Id of the Quote to price.

 |
| 

`rootLineId`

 | 

Required.

Id of the `QuoteLineItem` to price.

 |
| 

`calculateTaxesAndFees`

 | 

Optional.

Set to `true` for the service to calculate taxes and fees.

Default value is `true`.

 |
| `withTaxFeeRounding` | 

Optional.

If true, the calculated tax and fee amounts are rounded to two decimal places by using the half even rounding method. `withTaxFeeRounding` is effective only when the `calculateTaxesAndFees` option is also true. If false, rounding is disabled.

Default value is false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

```json
{
  "quoteId": "0Q05w000001mgQNCAY",
  "rootLineId": "0QL5w000003kyBnGAI"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

```json
{
  "calculatedTaxesAndFees": {
    "0QL5w0000044u0UGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0SGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0RGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0QGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0PGAQ": {
      "feeAmount": 25,
      "taxAmount": 157.5
    },
    "0QL5w0000044u0KGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0IGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0HGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0GGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0FGAQ": {
      "feeAmount": 25,
      "taxAmount": 157.5
    },
    "0QL5w0000044u0BGAQ": {
      "feeAmount": null,
      "taxAmount": null
    },
    "0QL5w0000044u0AGAQ": {
      "feeAmount": 50,
      "taxAmount": 315
    }
  },
  "calculatedPrice": {
    "0QL5w0000044u0SGAQ": 500,
    "0QL5w0000044u0RGAQ": 575,
    "0QL5w0000044u0QGAQ": 0,
    "0QL5w0000044u0IGAQ": 500,
    "0QL5w0000044u0HGAQ": 575,
    "0QL5w0000044u0GGAQ": 0,
    "0QL5w0000044u0FGAQ": 1575,
    "0QL5w0000044u0KGAQ": 0,
    "0QL5w0000044u0PGAQ": 1575,
    "0QL5w0000044u0UGAQ": 0,
    "0QL5w0000044u0BGAQ": 0,
    "0QL5w0000044u0AGAQ": 3150
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo