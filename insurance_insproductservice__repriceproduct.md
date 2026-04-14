---
title: "InsProductService:repriceProduct"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductService:repriceProduct

InsProductService:repriceProduct[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductService:repriceProduct

Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsProductService`

Method: `repriceProduct`

The service takes one product object in its input JSON and returns the product with total pricing and total insured sum. It also returns the complete result JSON from the rating procedure.

This service works for one or more insured parties (people covered by the policy product) and one or more insured items (multiple cars on an auto policy, for example).

This service doesn't run Eligibility, Required, and Default optional coverage rules when modifying a quote.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service searches the input JSON for the selected product key, then retrieves its value. This object contains one product object.
    
2.  Using the product data to search Salesforce, the service finds the product and retrieves the rating procedure.
    
3.  The service rates the product with the product JSON structure.
    
4.  The service returns the product objects with total price and total insured sum. The output JSON includes the parsed result JSON from the rating procedure as the value of `CalculatedPriceData`. The service also sets price and `totalSumInsured` if the formulas are set on the product.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`aggByKey`

 | 

`PRODUCT.instanceKey`

When `aggByKey` is set, its value is included in the `aggregationResult` of the calculation procedure, if `aggregationResult` is not empty. (The `aggregationResult` is usually populated when a calculation procedure has aggregation steps configured).

For example, an auto insurance quote or policy has multiple drivers attached to each insured auto. The insured auto has a separate `instanceKey` for each auto+driver instance. The `aggByKey` takes the all the `instanceKeys` for the vehicles and creates an array of coverage premiums per `instanceKey`, and passes them to the calculation procedure so that premiums can be calculated correctly.

 |
| 

`alwaysCreateInstance`

 | 

Set this option to `true` for products with multiple child specs in a given level of the hierarchy, no grandchild specs, and only one rating procedure at the root level.

Omit this option for products that don't meet all these criteria.

To format `userInputs` for this type of product, see [One Rating Procedure per Product for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_one_rating_procedure_per_product.htm&language=en_US&type=5 "Format InsProductService:repriceProduct userInputs for products that use a single rating procedure per root product.").

 |
| 

`effectiveDate`

 | 

`“YYYY-MM-DD HH:MM:SS”`

or

%OmniScriptDataElement%

Defaults to today's date.

 |
| 

`evalOptionalCoverageRelationship`

 | 

`true` or `false`

If this option = `true`, the service calls `updateOptionalCovIsSelectedField` first, then calls `repriceProduct`.

 |
| 

`getDataDRBundleName`

 | 

The name of the Omnistudio Data Mapper this service uses to retrieve policy (asset) information.

If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| 

`getDataCustomClassName`

 | 

The name of the custom class this service uses to retrieve policy (asset) information.

If you're using Salesforce FSC, you must specify either this option or `getDataDRBundleName`.

 |
| 

`includeInputKeys`

 | 

A string of comma-separated key/value pairs that the service passes into and out of the calculation procedure.

These key/value pairs are included in the output product object within the `CalculatedPriceData` object. They're there to help you parse the calculation results.

Only input keys used by the calculation procedure have a value in the results.

 |
| 

`includeRawCalculationResult`

 | 

`true` or `false`

Defaults to `false`.

Includes the entire results of calculation procedure in the `RawPriceData` key.

 |
| 

`validateCoverageSelection`

 | 

`true` or `false`

Set to `true` if you plan to use optional coverage validation rules. When this option is set to `true`, the service calls `InsuranceSelectValidationService` before calling reprice.

 |
| 

`calculateTaxesAndFees`

 | 

Optional

`true` or `false`

Set to `true` to calculate taxes and fees on the target product.

[](https://help.salesforce.com/s?language=en_US)If you use Salesforce FSC and you set this option to `true`, you must also specify `getDataDRBundleName` or `getDataCustomClassName` option.

 |
| 

`jurisdictionIds`

 | 

Stringifed list of ids

Used in conjunction with `calculateTaxesAndFees` option.

Calculates only the taxes and fees associated with the provided jurisdictions.

 |
| `taxAndFeeEffectiveDate` | 

The effective date this service uses to calculate taxes and fees. This option is separate from the `effectiveDate` option used to Price the product.

If a value is provided, the service uses that value.

If a value is not provided and the product JSON is not a policy, the service defaults to today’s date.

If value is not provided and the product JSON is a policy, the service uses the original policy version’s effective date.

 |
| `withTaxFeeRounding` | 

Optional

If true, the calculated tax and fee amounts are rounded to two decimal places by using the half even rounding method. `withTaxFeeRounding` is effective only when the `calculateTaxesAndFees` option is also true. If false, rounding is disabled.

Default value is false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

`InsProductService: repriceProduct` looks for a product object in the `selectedProduct` key in its input JSON. This object contains the inputs needed by the rating procedure as mapped in the attributes of the product, including its associated coverage specs, insured item specs, insured party specs, and rating fact specs. This object can be created by other services like `getRatedProducts`. It includes the root product, child products, and grandchild products. The service parses the product structure and passes data into the expression set or calculation procedure. If attributes mapped for rating are not included in the object, the service uses defaults set by the product administrator.

This service also looks for a `userInputs` key in the input JSON, so it can find any rating factors that aren't included in the `selectedProduct` node. Use the appropriate `userInputs` format depending on the product definition and the rating configuration. The service accepts only one type of `userInputs` format at a time.

-   [One Rating Procedure per Product for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_one_rating_procedure_per_product.htm&language=en_US&type=5 "Format InsProductService:repriceProduct userInputs for products that use a single rating procedure per root product.")
    
-   [Multiple Rating Procedures per Product or Multiple Specs at Any Level for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_multi_rating_procs_per_product_or_multi_specs_at_any_level.htm&language=en_US&type=5 "Format InsProductService:repriceProduct userInputs for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.")
    

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the same JSON structure as that in the `selectedProduct` node with updated pricing information. See [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.") for details about the contents and structure of this object.

Note

If taxes and fees services are used, JSON output is persisted onto the JSON record, similar to the way `getRatedProducts` writes to the JSON.

For each product, the output JSON from the rating procedure calculation is added to the product with the `CaculatedPriceData` key. If the pricing formula is set on the product, the value of `price` is set to its calculated value. If the total insured formula is set on the product, the value of `TotalInsured` is set to its calculated value.

The structure under `CalculatedPriceData`, includes instance support. Price metrics are grouped under instance level.

The output JSON includes a `priceDiff` node at root level that sums up instance level prices. It also includes the `totalPremiumForTermDiff` field at the root level. This value is the difference between the original total premium for term and the sum between the total premium for term of the new policy version and the updated premium for term of the old policy version.

In this example, the pricing formula is set on the product, but the total insured formula is not. The service adds the `CalculatedPriceData` to the results from the rating procedure. The service calculates the price based on the formula. The total insured formula is not set on the product and does not appear in the data (neither does `TotalInsured`).

```
"totalSize": null,
"records": [{
    "displaySequence": -1,
    "rootProductId": "01t1I000002fuBoQAI",
    "rootProductCode": "AUTOROOT",
    "timestamp": 1533948385704,
    "hasInstanceKeys": true,
    "childProductsCount": 8,
    "instanceKeyChildren": 2,
    "pathFromChild": "[0]",
    "pathFromRoot": "[0]",
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
        "calculationResults": [{
          "DRIVER.LN": null,
          "DRIVER.FN": null,
          "AUTO.instanceKey": "2015 Lexus LX250",
          "uninsuredMotoristBITotal": 100,
          "uninsuredMotoristPDTotal": 0,
          "dedWaiverTotal": 10,
          "roadsideTotal": 10,
          "medicalTotal": 10,
          "rentalTotal": 40,
          "comprehensiveTotal": 500,
          "ID": "0"
        }],
        "aggregationResults": {}
      },
      {
        "calculationResults": [{
          "DRIVER.LN": null,
          "DRIVER.FN": null,
          "AUTO.instanceKey": "2006 Honda Odyssey",
          "uninsuredMotoristBITotal": 100,
          "uninsuredMotoristPDTotal": 0,
          "dedWaiverTotal": 10,
          "roadsideTotal": 10,
          "medicalTotal": 10,
          "rentalTotal": 40,
          "comprehensiveTotal": 500,
          "ID": "1"
        }],
        "aggregationResults": {}
      }
    ],
    "CalculatedPriceData": {
      "2015 Lexus LX250": {
        "DRIVER.LN": null,
        "DRIVER.FN": null,
        "AUTO.instanceKey": "2015 Lexus LX250",
        "uninsuredMotoristBITotal": 100,
        "uninsuredMotoristPDTotal": 0,
        "dedWaiverTotal": 10,
        "roadsideTotal": 10,
        "medicalTotal": 10,
        "rentalTotal": 40,
        "comprehensiveTotal": 500,
        "ID": "0"
      },
      "2006 Honda Odyssey": {
        "DRIVER.LN": null,
        "DRIVER.FN": null,
        "AUTO.instanceKey": "2006 Honda Odyssey",
        "uninsuredMotoristBITotal": 100,
        "uninsuredMotoristPDTotal": 0,
        "dedWaiverTotal": 10,
        "roadsideTotal": 10,
        "medicalTotal": 10,
        "rentalTotal": 40,
        "comprehensiveTotal": 500,
        "ID": "1"
      }
    },
    "priceDiff": 0,
    "totalPremiumForTermDiff": 0,
    "attributeCategories": {
      "totalSize": 1,
      "records": [{
        "displaySequence": 5,
        "id": "a1V1I0000007xJSUAY",
        "Name": "Alan Health Attributes",
        "Code__c": "AHA",
        "productAttributes": {
          "totalSize": 1,
          "records": [{
            "code": "ALANDEDUCTIBLE",
            "dataType": "text",
            "inputType": "text",
            "required": false,
            "readonly": false,
            "disabled": false,
            "filterable": true,
            "attributeId": "a1W1I000000Bu1jUAC",
            "label": "Deductible",
            "displaySequence": 2,
            "hasRules": false,
            "hidden": false,
            "values": [{
              "readonly": false,
              "disabled": false
            }],
            "userValues": "test",
            "parentProductId": "01t1I000002fuBoQAI",
            "parentProductCode": "AUTOROOT",
            "pathFromChild": "attributeCategories.records[0].productAttributes.records[0]",
            "pathFromRoot": "attributeCategories.records[0].productAttributes.records[0]"
          }]
        }
      }]
    },
    "childProducts": {
      ...
    }
```

-   **[One Rating Procedure per Product for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_one_rating_procedure_per_product.htm&language=en_US&type=5)**  
    Format `InsProductService:repriceProduct userInputs` for products that use a single rating procedure per root product.
-   **[Multiple Rating Procedures per Product or Multiple Specs at Any Level for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_multi_rating_procs_per_product_or_multi_specs_at_any_level.htm&language=en_US&type=5)**  
    Format `InsProductService:repriceProduct userInputs` for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.

Did this article solve your issue?

Let us know so we can improve!

YesNo