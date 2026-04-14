---
title: "InsProductJSONService:updateUserValues"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__updateuservalues.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductJSONService:updateUserValues

InsProductJSONService:updateUserValues[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductJSONService:updateUserValues

Use this service to update the `userValues` of specified attributes in a product JSON, based on changes a user has made. You can also use this service to update where the JSON node is in the hierarchy.

Note This service can be used to update the JSON, but will not change the product definition itself.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsProductJSONService`

Method: `updateUserValues`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Uses the `inputKey` and `attributeValues` to find the node in the input JSON with the attributes to be updated.
    
2.  If `productCode` and/or `attributeCode` are set, the service filters the JSON to match.
    
3.  Validates the new attribute value against possible attribute values, if `validate = true`.
    
4.  Returns the product JSON with the updated attributes.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`inputKey`

 | 

The key this service uses to find the part of the product JSON to work with.

The default value is `inputKey`.

 |
| 

`productCode`

 | 

Finds attributes directly associated with this `productCode`.

 |
| 

`attributeCode`

 | 

Finds the attribute specified by this `attributeCode`.

 |
| 

`patternMatch`

 | 

True/false

Works with a partial value specified for atttributeCode to find an attribute.

Default = `false`

 |
| 

`instanceKey`

 | 

Finds the attributes associated with the product (and the child products) that has this `instanceKey`.

 |
| 

`validate`

 | 

True/false

Validates new attribute values against all allowed values for a given attribute before updating the JSON.

Default = `false`

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service takes a typical product JSON it identifies using the `inputKey` and `attributeValues` in the form of a map of the `attributeCode` and the new `userValues`.

To learn how product JSONs are structured, see [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.").

From the example below, the attributes value of `liveCoverageAmt` is $250,000. And in "attributeValues" it is to be changed to $500,000.

```
{
  "inputKey": {
    "totalSize": 1,
    "records": [
      {
        "Name": "Product1",
        "ProductCode": "Product1",
        "attributeCategories": {
          "totalSize": 1,
          "records": [
            {
              "displaySequence": 449,
              "id": "a0O6A000001XFIPUA4",
              "Name": "Life Terms",
              "Code__c": "LIFETERMS",
              "productAttributes": {
                "totalSize": 1,
                "records": [
                  {
                    "code": "lifeCoverageAmt",
                    "dataType": "text",
                    "inputType": "dropdown",
                    "multiselect": false,
                    "required": false,
                    "readonly": false,
                    "disabled": false,
                    "filterable": true,
                    "attributeId": "a0P6A0000032HllUAE",
                    "label": "Coverage Amount",
                    "displaySequence": 1,
                    "hasRules": false,
                    "hidden": false,
                    "values": [
                      {
                        "id": "0",
                        "label": "$250,000",
                        "readonly": false,
                        "disabled": false,
                        "value": "250000"
                      },
                      {
                        "id": "1",
                        "label": "$500,000",
                        "readonly": false,
                        "disabled": false,
                        "value": "500000"
                      },
                      {
                        "id": "2",
                        "label": "$1,000,000",
                        "readonly": false,
                        "disabled": false,
                        "value": "1000000"
                      }
                    ],
                    "userValues": "250000",
                    "parentProductId": "a2mf4000000kYR7AAM",
                    "parentProductCode": "InsLife",
                    "originalAttributeIndex": 0,
                    "originalCategoryIndex": 1,
                    "originalProductIndex": 1,
                    "pathFromChild": "attributeCategories.records[1].productAttributes.records[0]",
                    "pathFromRoot": "\"pathFromRoot\": \"childProducts.records[1].attributeCategories.records[1].productAttributes.records[0]\""
                  }
                ]
              }
            }
          ]
        }
      }
    ]
  },
  "attributeValues": {
    "lifeCoverageAmt": "500000"
  }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an updated product JSON with the new attribute values under the `result` key and information about the original attribute value.

In the following example, the value for the `liveCoverageAmt` attribute was changed from $250,000 to $500,000.

```
{
  "records": [
    {
      "attributeCategories": {
        "records": [
          {
            "productAttributes": {
              "records": [
                {
                  "pathFromRoot": "\"pathFromRoot\": \"childProducts.records[1].attributeCategories.records[1].productAttributes.records[0]\"",
                  "pathFromChild": "attributeCategories.records[1].productAttributes.records[0]",
                  "originalProductIndex": 1,
                  "originalCategoryIndex": 1,
                  "originalAttributeIndex": 0,
                  "parentProductCode": "InsLife",
                  "parentProductId": "a2mf4000000kYR7AAM",
                  "userValues": "500000",
                  "values": [
                    {
                      "value": "250000",
                      "disabled": false,
                      "readonly": false,
                      "label": "$250,000",
                      "id": "0"
                    },
                    {
                      "value": "500000",
                      "disabled": false,
                      "readonly": false,
                      "label": "$500,000",
                      "id": "1"
                    },
                    {
                      "value": "1000000",
                      "disabled": false,
                      "readonly": false,
                      "label": "$1,000,000",
                      "id": "2"
                    }
                  ],
                  "hidden": false,
                  "hasRules": false,
                  "displaySequence": 1,
                  "label": "Coverage Amount",
                  "attributeId": "a0P6A0000032HllUAE",
                  "filterable": true,
                  "disabled": false,
                  "readonly": false,
                  "required": false,
                  "multiselect": false,
                  "inputType": "dropdown",
                  "dataType": "text",
                  "code": "lifeCoverageAmt"
                }
              ],
              "totalSize": 1
            },
            "Code__c": "LIFETERMS",
            "Name": "Life Terms",
            "id": "a0O6A000001XFIPUA4",
            "displaySequence": 449
          }
        ],
        "totalSize": 1
      },
      "ProductCode": "Product1",
      "Name": "Product1",
      "displaySequence": -1
    }
  ],
  "totalSize": 1
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo