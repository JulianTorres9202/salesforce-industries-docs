---
title: "One Rating Procedure per Product for repriceProduct"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_one_rating_procedure_per_product.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# One Rating Procedure per Product for repriceProduct

One Rating Procedure per Product for repriceProduct[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# One Rating Procedure per Product for repriceProduct

Format `InsProductService:repriceProduct userInputs` for products that use a single rating procedure per root product.

Note

For most products that use multiple rating procedures in the product hierarchy or multiple specs in any level of the hierarchy, you format input JSON differently. See [Multiple Rating Procedures per Product or Multiple Specs at Any Level for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_multi_rating_procs_per_product_or_multi_specs_at_any_level.htm&language=en_US&type=5 "Format InsProductService:repriceProduct userInputs for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.").

Products configured before Winter '23 release 240.22 can have multiple child specs in a given level of the hierarchy, no grandchild specs, and only one rating procedure at the root level. For these products, use the same `userInputs` format as you did in earlier releases.

To prevent errors, run the service with only one type of `userInputs` format at a time.

[](https://help.salesforce.com/s?language=en_US)Beginning in Summer '20, input JSON accepts an `additionalInputs` node. Use this node to set `stage` as an additional input so that the system evaluates stage correctly when the service runs.

Note

Eligibility rules are not supported.

For any product, the target format for the `userInputs` object can be obtained from the service listing in the API tab of the product view. The object keys are in the form `"<ProductCode>.<AttributeCode>"` where the ProductCode is the code of the product or the product code of associated coverage specs, insured item specs, or rating facts.

The `<productCode>.isSelected` of the coverage is also available for use in the expression set or calculation procedure.

Note

This service supports only one object in its records array.

```
{
  "selectedProduct": {
    "records": [{
      "rootProductId": "01t1I000002fuBoQAI",
      "rootProductCode": "AUTOROOT",
      "timestamp": 1533948385704,
      "hasInstanceKeys": true,
      "childProductsCount": 8,
      "instanceKeyChildren": 2,
      "pathFromChild": "[0]",
      "pathFromRoot": "[0]",
      "attributeCategories": {
        ...
      }
      "childProducts": {
        ...
      }
      "Price": 80,
      "productId": "01t1I000002fuBoQAI",
      "Term__c": "Semi-Annual",
      "PricingFormula__c": "SUM(AutoPremium__autoPremium + rentalTotal + medicalTotal + roadsideTotal + dedWaiverTotal + uninsuredMotoristPDTotal + uninsuredMotoristBITotal)",
      "IsConfigurable__c": true,
      "RecordTypeName__c": "Product",
      "IsRecommended__c": false,
      "ProductCode": "AUTOROOT",
      "Name": "Auto Root",
      "Id": "01t1I000002fuBoQAI",
      "RawPriceData": [{
          "aggregationResults": {},
          "calculationResults": [{
              "ID": "0",
              "comprehensiveTotal": 500,
              "rentalTotal": 40,
              "medicalTotal": 10,
              "roadsideTotal": 10,
              "dedWaiverTotal": 10,
              "uninsuredMotoristPDTotal": 0,
              "uninsuredMotoristBITotal": 100,
              "AUTO.instanceKey": "2015 Lexus LX250",
              "DRIVER.FN": "Joan",
              "DRIVER.LN": "Smith"
            },
            {
              ...
            }
          ]
        },
        {
          "aggregationResults": {},
          "calculationResults": [{
              "ID": "4",
              "comprehensiveTotal": 500,
              "rentalTotal": 40,
              "medicalTotal": 10,
              "roadsideTotal": 10,
              "dedWaiverTotal": 10,
              "uninsuredMotoristPDTotal": 0,
              "uninsuredMotoristBITotal": 100,
              "AUTO.instanceKey": "2006 Honda Odyssey",
              "DRIVER.FN": "Joan",
              "DRIVER.LN": "Smith"
            },
            {
              ...
            }
          ]
        }
      ],
      "CalculatedPriceData": {
        "2006 Honda Odyssey": {
          "ID": "4",
          "comprehensiveTotal": 500,
          "rentalTotal": 40,
          "medicalTotal": 10,
          "roadsideTotal": 10,
          "dedWaiverTotal": 10,
          "uninsuredMotoristPDTotal": 0,
          "uninsuredMotoristBITotal": 100,
          "AUTO.instanceKey": "2006 Honda Odyssey",
          "DRIVER.FN": "Joan",
          "DRIVER.LN": "Smith"
        },
        "2015 Lexus LX250": {
          "ID": "0",
          "comprehensiveTotal": 500,
          "rentalTotal": 40,
          "medicalTotal": 10,
          "roadsideTotal": 10,
          "dedWaiverTotal": 10,
          "uninsuredMotoristPDTotal": 0,
          "uninsuredMotoristBITotal": 100,
          "AUTO.instanceKey": "2015 Lexus LX250",
          "DRIVER.FN": "Joan",
          "DRIVER.LN": "Smith"
        }
      },
      "displaySequence": -1
    }]
  }
}
```

Note

An alternate approach is to define an Omnistudio Data Mapper transform that maps the data that's passed into the input JSON into the form the service needs. This Data Mapper's output JSON is `selectedProducts` node required by `repriceProduct`, and the `userInputs` JSON defined in the product view API tab. To set up the service to use the Data Mapper, set the `preTransformBundle` option to the name of the Data Mapper.

Did this article solve your issue?

Let us know so we can improve!

YesNo