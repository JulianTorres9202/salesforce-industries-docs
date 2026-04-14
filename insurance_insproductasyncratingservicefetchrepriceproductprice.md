---
title: "InsProductAsyncRatingService:fetchRepriceProductPrice"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductasyncratingservicefetchrepriceproductprice.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductAsyncRatingService:fetchRepriceProductPrice

InsProductAsyncRatingService:fetchRepriceProductPrice[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductAsyncRatingService:fetchRepriceProductPrice

Use this service to fetch asynchronous rating results for a reprice product request.

Class: `InsProductAsyncRatingService`

Method: `fetchRepriceProductPrice`

This service is built for group benefits large group quoting use cases.

## How It Works

1.  This service takes the ID of an insurance rating request as input.
2.  The service queries the stored rating request and retrieves info including the status, rated product IDs, rating options, rating inputs, rating outputs and the `prodResultJson` associated with the `insuranceRatingRequestId`.
    
    Note Prices for rated products are provided by the service only if the rating request has a status of Completed or Rated.
    
3.  The service calculates the total prices for the product associated with the submitted `repriceProduct` request.
4.  The service returns the updated `prodResultJson`.

## Inputs

| Input | Description |
| --- | --- |
| `requestId` | 
Required.

The ID of the insurance rating request. This ID is generated when the service is called.

 |

## Remote Options

| Option | Description |
| --- | --- |
| `includeMemberPrices` | 
Indicates whether or not to include the member-level prices in the output.

The default value is `false`.

 |

## Input JSON

Here's the sample input JSON:

```json
{
 "requestId": "8zkRO000000004D",
}
```

## Options JSON

Here's the sample options JSON:

```json
{    
  "includeMemberPrices": false
} 
```

## Output JSON

Here's the sample output JSON:

```json
{
    "Status": "Completed", 
    "result":
    {
        "totalSize": 2,
        "records": [
        {
            "nameResult": {
                "childProducts": {},
                "attributeCategories": {}
            },
            "fields": {
                "Price": 325.0,
                "currencySymbol": "$",
                "currencyCode": "USD",
                "productId": "01t8c00000P49yeAAB",
                "ParentClassCode__c": null,
                "ParentClassId__c": null,
                "TotalInsuredFormula__c": null,
                "Term__c": null,
                "PricingFormula__c": "aggTotalPrem",
                "IsConfigurable__c": true,
                "RecordTypeName__c": "Product",
                "PricingSource__c": null,
                "ImageId__c": null,
                "Tier__c": null,
                "IsRecommended__c": false,
                "RateBandId__c": null,
                "SubType__c": null,
                "Type__c": null,
                "MarketSegment__c": null,
                "LineOfBusiness__c": "Group Benefits",
                "ProductCode": "dentalPremium",
                "Family": null,
                "Description": null,
                "Name": "dentalPremium",
                "Id": "01t8c00000P49yeAAB",
                "CalculatedPriceData": {
                      "aggTotalPrem": 325.0,
                      "DentalPremiumCalcMatrixAgeBased__QuotePremium": 325.0
                }
            },
            "displaySequence": -1
        },
        {
            "nameResult": {
                "childProducts": {},
                "attributeCategories": {}
            },
            "fields": {
                "Price": 1020.0,
                "currencySymbol": "$",
                "currencyCode": "USD",
                "productId": "01t8c00000PLIiEAAX",
                "ParentClassCode__c": null,
                "ParentClassId__c": null,
                "TotalInsuredFormula__c": null,
                "Term__c": null, 
                "PricingFormula__c": "aggTotalPrem",
                "IsConfigurable__c": true,
                "RecordTypeName__c": "Product",
                "PricingSource__c": null,
                "ImageId__c": null,
                "Tier__c": null,
                "IsRecommended__c": false,
                "RateBandId__c": null,
                "SubType__c": null,
                "Type__c": "Medical",
                "MarketSegment__c": null,
                "LineOfBusiness__c": "Group Benefits",
                "ProductCode": "MEDICAL",
                "Family": null,
                "Description": null,
                "Name": "Medical",
                "Id": "01t8c00000PLIiEAAX",
                "CalculatedPriceData": {
                    "aggTotalPrem": 325.0,
                    "MedicalCalcMatrixAgeBased__QuotePremium": 325.0 
                }
            },
            "displaySequence": -1
        }
        ]
    }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo