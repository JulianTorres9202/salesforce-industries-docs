---
title: "InsProductAsyncRatingService:repriceProduct"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicerepriceproduct.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductAsyncRatingService:repriceProduct

InsProductAsyncRatingService:repriceProduct[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductAsyncRatingService:repriceProduct

Asynchronously recalculate the price of a product based on `selectedProduct` JSON and `userInput`.

Class: `InsProductAsyncRatingService`

Method: `repriceProduct`

This service is built for Group Benefit Large Volume Product Rating use cases.

## How It Works

1.  This service takes `selectedProduct` JSON, `userInput`, and the `censusId`
2.  Next, the service looks at the product to determine if it's configured for Census Based Rating or Summary Based Rating (based on the `PricingStrategyType__c` field).
3.  The service calls the `InsuranceRatingPtc.rateCensus` Core service to calculate the price for all the products. The `InsuranceRatingPtc.rateCensus` service is an asynchronous service so it doesn't return the price immediately. Instead, it returns an `asyncRequestId`.

## Inputs

| Input | Description |
| --- | --- |
| `groupClassIds` | 
Optional.

A list of group class IDs.

 |
| `productCategories` | 

Optional.

A list of product categories. The sequence should be the same as `productIds`

 |
| `selectedProduct` | 

Required.

The product to be repriced.

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
| `evalOptionalCoverageRelationship` | Determines whether to evaluate optional coverages available for a participant based on their relationship to the primary census member. If this option is set to `true`, the service first calls `updateOptionalCovIsSelectedField`, and then calls `repriceProduct`. |
| `ruleAttributeSetValues` | Determines whether to run Set Value rules. If this option is set to `true`, the service runs attribute Set Value rules before calling the pricing engine. |
| `validateCoverageSelection` | Determines whether to run coverage validation rules on the selected coverages. When this option is set to `true`, the service calls `InsuranceSelectValidationService` before calling `repriceProduct`. |

## Input JSON

Here's the sample input JSON:

```json
{
 "userInputs": {"DentalCoverage.copay": 100},
 "groupClassIds": ["0rEDI0000000IEe2AM", "0rEDI0000000IEe4Hr"],
 "productCategories": ["Dental"],
 "selectedProduct": {
   "records": [
    {
      "displaySequence": -1,
      "CalculatedPriceData": {
        "2015 Lexus LX250": {
          " DRIVER.FN": null,
          "AUTO.instanceKey": "2015 Lexus LX250",
          "totalPrice": 1650,
          "comprehensiveTotal": 500,
          "collisionTotal": 500,
          "liabilityTotal": 650,
          "totalTotal": 400,
          "perAccidentTotal": 150,
          "perPersonTotal": 100,
          "ID": "1"
        }
      },
      "Id": "01tB0000001qc4JIAQ",
      "Name": "Auto Root",
      "ProductCode": "AUTOROOT",
      "IsRecommended__c": false,
      "RecordTypeName__c": "Product",
      "IsConfigurable__c": false,
      "PricingFormula__c": "SUM(liabilityTotal + comprehensiveTotal + collisionTotal + stateTotal)",
      "Term__c": "Annual",
      "TotalInsuredFormula__c": "SUM(AUTO.carValue)",
      "productId": "01tB0000001qc4JIAQ",
      "currencyCode": "USD",
      "currencySymbol": "$",
      "Price": 1000,
      "totalSumInsured": 0,
      "taxesAndFees": [
        {
          "calculatedAmount": 100,
          "currencySymbol": "$",
          "currencyCode": "USD",
          "Type__c": "Fee",
          "RatingType__c": "Amount",
          "ProcedureSource__c": null,
          "ProcedureName__c": null,
          "ProcedureFormula__c": null,
          "Percent__c": null,
          "JurisdictionId__c": null,
          "IsRefundable__c": false,
          "Condition__c": null,
          "Amount__c": 100,
          "Name": "acaf9c93-67b1-5a94-c98f-e7a1387361f1",
          "Id": "a4OB0000000ErbeMAC"
        },
        {
          "calculatedAmount": 50,
          "currencySymbol": "$",
          "currencyCode": "USD",
          "Type__c": "Tax",
          "RatingType__c": "Percent",
          "ProcedureSource__c": null,
          "ProcedureName__c": null,
          "ProcedureFormula__c": null,
          "Percent__c": 5,
          "JurisdictionId__c": null,
          "IsRefundable__c": true,
          "Condition__c": null,
          "Amount__c": null,
          "Name": "c4b50dd7-7b28-27c0-8b9f-87cd68e6a478",
          "Id": "a4OB0000000ErbfMAC"
        }
      ],
      "taxAmount": 160,
      "feeAmount": 145,
      "totalTaxFeeAmount": 305,
      "childProducts": {
        "totalSize": 2,
        "records": [
          {
            "displaySequence": 1,
            "Id": "01tB0000001qc5lIAA",
            "Name": "Collision Deductible Waiver",
            "Description": "We waive your Collision deductible when you're in an accident caused by a driver who has no insurance.",
            "ProductCode": "COL_WAIVER",
            "IsRecommended__c": false,
            "RecordTypeName__c": "CoverageSpec",
            "IsConfigurable__c": true,
            "productId": "01tB0000001qc5lIAA",
            "pciId": "a4bB0000000CzkzIAC",
            "isOptional": false,
            "isSelected": true,
            "attributeCategories": {
              "totalSize": 1,
              "records": [
                {
                  "displaySequence": 1981,
                  "Code__c": "AUTO_COVERAGE",
                  "Name": "Auto Coverage",
                  "productAttributes": {
                    "totalSize": 1,
                    "records": [
                      {
                        "code": "DED_WAIVER",
                        "dataType": "text",
                        "inputType": "dropdown",
                        "multiselect": false,
                        "required": false,
                        "readonly": false,
                        "disabled": false,
                        "filterable": true,
                        "label": "Collision Deductible Waiver",
                        "displaySequence": 3,
                        "hasRules": false,
                        "hidden": false,
                        "values": [
                          {
                            "id": "0",
                            "label": "No coverage",
                            "readonly": false,
                            "disabled": false,
                            "value": "No coverage"
                          },
                          {
                            "id": "1",
                            "label": "$1,000 deductible",
                            "readonly": false,
                            "disabled": false,
                            "value": "1000"
                          }
                        ],
                        "userValues": "No coverage"
                      }
                    ]
                  }
                }
              ]
            }
          }
        ]
      }
    }
  ]
 }
}
```

## Options JSON

Here's the sample options JSON:

```json

{     
  "censusId": "0rfRO00000009WTYAY",
  "effectiveDate": "2023-06-22 00:00:00"
}
```

## Output JSON

Here's the sample output JSON:

```json
{
  "asyncRequestId": {
    "01tRO000000k6RyYAI": "8zk9f00000Q5jUEHNS"
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo