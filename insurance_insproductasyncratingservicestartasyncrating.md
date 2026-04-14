---
title: "InsProductAsyncRatingService:startAsyncRating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicestartasyncrating.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductAsyncRatingService:startAsyncRating

InsProductAsyncRatingService:startAsyncRating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductAsyncRatingService:startAsyncRating

Asynchronously calculate product prices based on a list of product IDs.

Class: `InsProductAsyncRatingService`

Method: `startAsyncRating`

This service is built for Group Benefit Large Volume Product Rating use cases.

## How It Works

1.  The service takes a list of product IDs.
2.  The service determines if each product is configured for Census Based Rating or Summary Based Rating (based on the `PricingStrategyType__c` field) .
3.  The service calls the `InsuranceRatingPtc.rateCensus` service to calculate the price for all the products The `InsuranceRatingPtc.rateCensus` service is an asynchronous service so it doesn't return the price immediately. Instead, it returns an `asynRequestId` for each product.

## Inputs

| Input | Description |
| --- | --- |
| `groupClassIds` | 
Optional.

A list of group class IDs. The sequence should be the same as `productIds`.

 |
| `productCategories` | 

Optional.

A list of product categories. The sequence should be the same as `productIds`.

 |
| `productIds` | 

Required.

A list of the product IDs.

 |
| `userInputs` | 

Required.

The set of input data the rating procedure uses to get the price of the product.

For a Map <String, Object>, the same set of input data is used for all of the products.

For a List<Map<String, Object>>, the size of the List should be the same as the size of `productIds`. If some products don't have a `userInput`, add a {} in the List.

Selecting coverages with `CoverageProductCode.isSelected` isn't supported, but it is taken into consideration when calculating pricing.

 |

## Remote Options

| Option | Description |
| --- | --- |
| `censusId` | 
Required.

The ID of the group census.

 |
| `effectiveDate` | 

The effective date used for rating.

Uses the "YYYY-MM-DD HH:MM:SS" format.

Default is today's date.

 |

## Input JSON

Here's the sample input JSON:

```json
{
  "productIds": ["01tRO000000k6RyYAI", "01t8a000006UC27AAG"],
  "userInputs": [{
                    "DentalCoverage.copay": 100
                 }, {
                    "CancerCoverage.deductible": 2000
   }],
   "groupClassIds": ["0rEDI0000000IEe2AM", "0rEDI0000000IEe4Hr"],
   "productCategories": ["Dental", "Medical"]
}
```

## Options JSON

Here's the sample options JSON:

```json
{     
  "censusId": "0rfRO00000009WTYAY",
  "effectiveDate": "2023-06-22 00:00:00",
  "calculateTaxesAndFees": true
}

```

## Output JSON

Here's the sample output JSON:

```json
{
  "asyncRequestId": {
    "01tRO000000k6RyYAI": "8zk9f00000Q5jUEHNS",
    "01t8a000006UC27AAG": "8zk9f00000Q5jUEYHQ"
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo