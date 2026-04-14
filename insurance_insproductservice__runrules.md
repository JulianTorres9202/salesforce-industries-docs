---
title: "InsProductService: runRules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__runrules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductService: runRules

InsProductService: runRules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductService: runRules

Use this service to run rules on a product without repricing that product.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsProductService`

Method: `runRules`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service searches the input JSON for the `selectedProduct` key.
    
2.  Runs the rules on `selectedProduct` node.
    
    Which sets of rules get run depends on which remote options are set to true.
    
3.  Returns the JSON with the results of the rules added to the `selectedProduct` node.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`ruleAttributeSetValues`

 | 

`true` or `false`

Defaults to `true`.

If true, service runs the attribute set value rules.

 |
| 

`evalOptionalCoverageRelationship`

 | 

`true` or `false`

Defaults to `false`.

When this option is set to `true`, the service evaluates the optional coverage relationship against the available rules and updates the `isSelected` flag on the affected optional coverage record.

 |
| 

`runDefaultSelected`

 | 

`true` or `false`

When set to true, runs default selected coverage rules for the selected product.

 |
| 

`runEligibility`

 | 

`true` or `false`

When set to true, runs eligibility rules for the selected product.

If the rules evaluate to `false`, the service sets the `isEligible` node in the optional coverage to `false`.

 |
| 

`runRequiredCoverage`

 | 

`true` or `false`

When set to true, runs optional coverage required coverage rules.

 |
| 

`validateCoverageSelection`

 | 

`true` or `false`

Defaults to false.

When this option is set to `true`, the service validates the optional coverage selection against available rules.

The service adds a message node to the affected optional coverage record if the rule evaluates to false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service looks for a product object in the `selectedProduct` key in its input JSON. This object can be created by other services like `getRatedProducts`. It includes the root product, child products, and grandchild products.

This example contains only one input node before the service runs the rules.

```

"Name": "Accidental Death",
                    "Description": "An accidental death benefit rider also known as a double indemnity clause provides a higher death benefit to the beneficiaries of the policy in case the insured dies because of an accident. The death benefit is generally a multiple of the face value of the base coverage.",
                    "Family": "Individual Life",
                    "ProductCode": "ADDCOV",
                    "LineOfBusiness__c": "Individual Health",
                    "Type__c": "Coverages",
                    "IsRecommended__c": false,
                    "PricingSource__c": "premiumADD",
                    "RecordTypeName__c": "CoverageSpec",
                    "IsConfigurable__c": true,
                    "productId": "01t1U000000OEamQAG",
                    "pciId": "a2w1U0000001G4YQAU",
                    "selectValidationCriteria": "[{\"expression\":\"WOP.isSelected == true\",\"code\":\"code_0\"}]",
                    "selectValidationMessage": "[{\"message\":\"WOP must be true\",\"severity\":\"INFO\",\"code\":\"code_0\"}]",
                    "isOptional": true,
                    "isSelected": true,
                    "parentInstanceKey": "Jack Kirkland",
                    "Price": 358,
                    "pathFromRoot": "[0].childProducts.records[2].childProducts.records[2]",
                    "formattedParentInstanceKey": "jack-kirkland",
                    "parentProductName": "Jack Kirkland",
                    "originalIndex": 2,
                    "numberCategories": 18,
                    "numberAttributes": 18,
                    "popoverOpen": false,
                    "isOriginalOptional": true,
                    "isAddedOptional": true,
                    "showTypeHeader": true,
                    "displaySequence": 1                 
```

[](https://help.salesforce.com/s?language=en_US)

## preTransformBundle Alternative

Alternately, you can define an Omnistudio Data Mapper transform that maps the data that's passed into the input JSON into the form the service needs. This Data Mapper’s output JSON is the `selectedProducts` node required by `runRules`. When you add this service to an OmniScript, set `preTransformBundle` to the name of the Data Mapper to have the service use the Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the same JSON structure as that in the `selectedProduct` node with the results of the rules run. See [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.") for details about the contents and structure of this object.

This example contains only one output node after the service runs the rules with the results of the rules run.

```
"messages": [
                    {
                      "code": "code_0",
                      "severity": "INFO",
                      "message": "WOP must be true"
                    }
                  ],
                  "displaySequence": 1,
                  "lastNonOptional": true,
                  "firstOptional": true,
                  "Id": "01t1U000000OEamQAG",
                  "Name": "Accidental Death",
                  "Description": "An accidental death benefit rider also known as a double indemnity clause provides a higher death benefit to the beneficiaries of the policy in case the insured dies because of an accident. The death benefit is generally a multiple of the face value of the base coverage.",
                  "Family": "Individual Life",
                  "ProductCode": "ADDCOV",
                  "LineOfBusiness__c": "Individual Health",
                  "Type__c": "Coverages",
                  "IsRecommended__c": false,
                  "PricingSource__c": "premiumADD",
                  "RecordTypeName__c": "CoverageSpec",
                  "IsConfigurable__c": true,
                  "productId": "01t1U000000OEamQAG",
                  "pciId": "a2w1U0000001G4YQAU",
                  "selectValidationCriteria": "[{\"expression\":\"WOP.isSelected == true\",\"code\":\"code_0\"}]",
                  "selectValidationMessage": "[{\"message\":\"WOP must be true\",\"severity\":\"INFO\",\"code\":\"code_0\"}]",
                  "isOptional": true,
                  "isSelected": true,
                  "parentInstanceKey": "Jack Kirkland",
                  "Price": 358,
                  "pathFromRoot": "[0].childProducts.records[2].childProducts.records[2]",
                  "formattedParentInstanceKey": "jack-kirkland",
                  "parentProductName": "Jack Kirkland",
                  "originalIndex": 2,
                  "numberCategories": 18,
                  "numberAttributes": 18,
                  "popoverOpen": false,
                  "isOriginalOptional": true,
                  "isAddedOptional": true,
                  "showTypeHeader": true,                                             
```                                             

Did this article solve your issue?

Let us know so we can improve!

YesNo