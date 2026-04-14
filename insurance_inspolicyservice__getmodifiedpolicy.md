---
title: "InsPolicyService:getModifiedPolicy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getModifiedPolicy

InsPolicyService:getModifiedPolicy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getModifiedPolicy

Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `getModifiedPolicy`

[](https://help.salesforce.com/s?language=en_US)

This service works with the Salesforce Financial Services Cloud.

Updates are provided via two nodes in the input: `modifiedItems` and `newInsuredItemsRelationships`.

Note The service can either add a new insured item or update attributes of an existing insured item but can't delete an item.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `assetId` or `policyId` of the policy to be modified.
    
2.  Takes a transformed JSON that contains an insured items map. This is a map of the insured items and parties on the target policy as well as all the modified attributes. This can also include new insured items that don’t currently exist on the target policy.
    
3.  Updates the insured item and insured party attribute values in the product JSON with those specified in the map of insured items. Adds new insured items to the product JSON.
    
    Note Adding optional coverages to insured items isn't supported by `InsPolicyService:getModifiedPolicy`.
    
4.  Processes any new associations between insured items or insured parties specified in the `newInsuredItemsRelationships` key and adds children products as needed in the product JSON. For example, a new association pairing a driver with a car results in a new child product under that specific car instance in the product JSON. 
    
    Tip
    
    Only new associations can be specified; existing associations can’t be removed with the info in the key.
    
5.  Uses the `aggByKey`, `effectiveDate`, `filters`, and `includeInputKey` options to reprice the policy and set the new prices in the product JSON.
    
6.  If calculating taxes and fees, only calculates taxes and fees for new records. For example, if an additional auto (insured item) is added to a policy, the service calculates new taxes and fees for the new auto. The rollup tax and fee values on the policy are updated.
    
    If no new insured items or coverages or added to the policy, taxes, and fees aren’t recalculated.
    
7.  Returns the product JSON with modified information. The `primaryParty` and `otherParties` nodes are created/updated if the child product is an Insured Party.
    
    Note
    
    If no `primaryParty` already exists, the `primaryParty` is created from the first new relationship specified in `newInsuredItemsRelationships` for the parent instance. Then the other new relationships in `newInsuredItemsRelationships` for the parent instance are added to the `otherParties` array.
    
    However, if the `primaryParty` already exists, the first new relationship specified in `newInsuredItemsRelationships` for the parent instance, as well as all other new relationships for that parent instance, are added to the `otherParties` array.
    
    This JSON includes the `taxesAndFees`, `taxAmount`, `feeAmount`, `totalTaxForTermDiff,` and `totalFeeForTermDiff` fields in the Policy JSON if the target Policy has taxes and/or fees.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    The JSON includes only the tax and/or fee fields that are used in this policy.
    

Note

All the remote options used in the [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service can also be used with this service.

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`modifiedItems`

 | 

The details on the updated insured items or insured parties).

 |
| 

`newInsuredItemsRelationships`

 | 

New associations between insured items and other items or insured parties, such as the addition of a driver to a car or the addition of jewelry to a home.

 |

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

PRODUCT.`instanceKey`

The service sends this option to a calculation procedure that includes an aggregation step, so that the calculation procedure returns the correct amount.

For example, an auto insurance policy has multiple drivers attached to each insured vehicle. The insured vehicle has a separate instanceKey for each instance in the policy. The aggByKey takes the all the instance keys for the vehicles and creates an array of coverage premiums per instanceKey, and passes them to the calculation procedure so that premiums can be calculated correctly.

The service uses this value to reprice the policy.

 |
| 

`assetId` or `policyId`

 | 

`%theIdYouNeed%`

The Id of policy being modified.

 |
| 

`effectiveDate`

 | 

`“YYYY-MM-DD HH:MM:SS”` or `%OmniScriptDataElement%`

The original effective date of the modified policy, used to reprice the policy.

 |
| 

`filters`

 | 

`Product2FieldName:Value,Product2FieldName:%Element Name%`

Use the API name with a colon followed by either a value or a variable. For example, in an OmniScript, a variable can be a name of an element, such as an input picklist.

Separate multiple filter parameters with commas.

Filters can include any field on the `Product2` object.

The service uses `filters` to reprice the policy.

 |
| 

`getDataDRBundleName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the Omnistudio Data Mapper this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| 

`getDataCustomClassName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataDRBundleName`.

 |
| 

`includeInputKeys`

 | 

A string of comma-separated keys to include in the output product object, within the `CalculatedPriceData` object.

Only keys used by the calculation procedure have a value in the results.

The service uses `includeInputKeys` to reprice the policy.

Note

This option has no relationship with the `inputKey` option.







 |
| 

`inputKey`

 | 

A key that tells us where to look for the modified insured items in the inputs map.

 |
| 

`calculateTaxesAndFees`

 | 

`true` or `false`

Calculates taxes and fees on the target product.

If set to true, recalculates all of the taxes and fees for the modified policy.

If you use Salesforce FSC and you set this option to `true`, you must also specify `getDataDRBundleName` or `getDataCustomClassName` option.

 |
| 

`ratingDate`

 | 

Determines the rating procedure for repricing the policy. If not provided, pricing is done based on the effective date of the modified policy.

Note You can't pass a specific time for ratingField as the field type is Date. So, the rating date timestamp defaults to 12:00 am.





 |
| 

`taxAndFeeEffectiveDate`

 | 

The effective date this service uses to calculate taxes and fees. This option is separate from the `effectiveDate` option used to Price the product.

If a value is provided, the service uses that value.

If a value isn’t provided and the product JSON isn’t a policy, the service defaults to today’s date.

 |
| 

`useLocalTimezone`

 | 

`true` or `false`

Defaults to `true`.

When set to `true`, this service uses the local timezone in which the policy version is created.

When set to `false`, this service uses GMT as the timezone.

 |
| `withTaxFeeRounding` | 

Optional

If true, the calculated tax and fee amounts are rounded to two decimal places by using the half even rounding method. `withTaxFeeRounding` is effective only when the `calculateTaxesAndFees` option is also true.

If false, rounding is disabled.

Default value is false.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here’s a sample of how to specify the `modifiedItems` and `newInsuredItemsRelationships` keys in the inputs map. `modifiedItems` should contain an array of instances for each product code with each instance's attribute data. `newInsuredItemsRelationships` should contain an array where each element is a map specifying the relationship between a child ( `instanceKey`) and its parent (`parentInstanceKey`).

```
"modifiedItems": {
  "DRIVER": [{
      "LN": "Smith",
      "GENDER": "Female",
      "FN": "Joan",
      "instanceKey": "Joan Smith",
      "AGE": 20
    },
    {
      "LN": "Smith",
      "GENDER": "Male",
      "FN": "John",
      "instanceKey": "John Smith",
      "AGE": 30
    },
    {
      "LN": "Henderson",
      "GENDER": "Male",
      "FN": "Robert",
      "instanceKey": "Robert Henderson",
      "AGE": 30
    },
    {
      "LN": "Schell",
      "GENDER": "Female",
      "FN": "Kinsey",
      "instanceKey": "Kinsey Schell",
      "AGE": 20
    }
  ],
  "AUTO": [{
      "VehicleType": "PASSENGER CAR",
      "BodyClass": "Sedan/Saloon",
      "autoYear": 2017,
      "autoModel": "LX350",
      "autoLicNum": "Lexus",
      "instanceKey": "2015 Lexus LX250"
    },
    {
      "VehicleType": "MULTIPURPOSE PASSENGER VEHICLE (MPV)",
      "BodyClass": "Minivan",
      "autoYear": 2006,
      "autoModel": "Odyssey",
      "autoLicNum": "Honda",
      "instanceKey": "2006 Honda Odyssey"
    },
    {
      "VehicleType": "PASSENGER CAR",
      "BodyClass": "Sedan/Saloon",
      "autoYear": 2018,
      "autoModel": "BMW",
      "autoLicNum": "530",
      "instanceKey": "2018 530 BMW"
    },
    {
      "VehicleType": "PASSENGER CAR",
      "BodyClass": "Sedan/Saloon",
      "autoYear": 2016,
      "autoModel": "Toyota",
      "autoLicNum": "Camry",
      "instanceKey": "2016 Camry Toyota"
    }
  ]
},
"newInsuredItemsRelationships": [
    {
      "instanceKey": "Joan Smith",
      "parentInstanceKey": "2015 Lexus LX250"
    },
    {
      "instanceKey": "Robert Henderson",
      "parentInstanceKey": "2018 530 BMW"
    }
  ]
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a product JSON with all the user modifications and additions included. It also includes calculated `priceDiff` and `totalPremiumForTermDiff` values that reflect the user modifications. For taxes and fees in particular, the `totalTaxForTermDiff` and `totalFeeForTermDiff` fields are also returned. They only appear when calculating taxes and fees, and represent the difference between the prorated tax or fee of the target policy and the prorated tax or fee of the modified policy (similar to the `totalPremiumForTermDiff` field).

```
{       
  "totalSize" : 1,
  "records" : [ {
    "displaySequence" : -1,
    "accountId" : "02i000000000000000",
    "EffectiveEnd" : "2019-12-31T08:00:00.000+0000",
    "EffectiveStart" : "2019-01-01T08:00:00.000+0000",
    "Name" : "policy",
    "policyNumber" : "4ec13580-2208-5109-095e-b39bdbaaeb56",
    "Price" : 25.50,
    "productId" : "01tRN000000LCquYAG",
    "RecordTypeName__c" : "Product",
    "term" : "Annual",
    "TotalPremiumForTerm__c" : 25.50,
    "totalSumInsured" : 19.25,
    "key" : "value",
    "feeAmount" : 10,
    "taxAmount" : 10,
    "nat_test__TotalFeeAmount__c" : 10,
    "TotalFeeForTerm__c" : 10.00,
    "nat_test__TotalTaxAmount__c" : 10,
    "TotalTaxForTerm__c" : 10.00,
    "hasAttributes" : false,
    "productName" : "AutoRoot",
    "ProductCode" : "AutoRoot",
    "currencyCode" : "USD",
    "currencySymbol" : "$",
    "taxesAndFees" : [ {
      "PriceListEntryName__c" : null,
      "PriceListEntryId__c" : "02i000000000000002",
      "isRefundable" : null,
      "Id" : null,
      "currencySymbol" : "$",
      "currencyCode" : "USD",
      "calculatedAmount" : 10,
      "Amount__c" : 10,
      "AdjustmentType__c" : "Tax"
    }, {
      "PriceListEntryName__c" : null,
      "PriceListEntryId__c" : "02i000000000000003",
      "isRefundable" : null,
      "Id" : null,
      "currencySymbol" : "$",
      "currencyCode" : "USD",
      "calculatedAmount" : 20,
      "Amount__c" : 20,
      "AdjustmentType__c" : "Fee"
    } ],
    "coverageCount" : 0,
    "childProducts" : {
      "totalSize" : 2,
      "records" : [ {
        "displaySequence" : -1,
        "hasAttributes" : true,
        "productName" : "Auto",
        "ProductCode" : "Auto",
        "nat_test__RecordTypeName__c" : "InsuredItemSpec",
        "productId" : "01tRN000000LCqrYAG",
        "Name" : "1998 Honda Civic",
        "instanceKey" : "1998 Honda Civic",
        "currencyCode" : "USD",
        "currencySymbol" : "$",
        "hasCoverages" : true,
        "primaryParty" : {
          "instanceKey" : "BobJones"
        },
        "otherParties" : [ {
          "productCode" : "Driver",
          "instanceKey" : "SarahJones",
          "LastName" : "Jones",
          "FirstName" : "Sarah"
        } ],
        "attributeCategories" : {
          "totalSize" : 1,
          "records" : [ {
            "displaySequence" : 1,
            "Code__c" : "Auto",
            "Name" : "Auto",
            "id" : "a0ZRN0000009TMm2AM",
            "productAttributes" : {
              "totalSize" : 3,
              "records" : [ {
                "code" : "Make",
                "dataType" : "text",
                "inputType" : "text",
                "multiselect" : false,
                "required" : false,
                "readonly" : false,
                "disabled" : false,
                "filterable" : true,
                "attributeId" : "a0aRN00000067pjYAA",
                "label" : "Make",
                "displaySequence" : -1,
                "hasRules" : false,
                "hidden" : false,
                "cloneable" : true,
                "isNotTranslatable" : false,
                "values" : [ {
                  "readonly" : false,
                  "disabled" : false
                } ],
                "userValues" : "Honda",
                "isNotAssetizable" : false
              }, {
                "code" : "Model",
                "dataType" : "text",
                "inputType" : "text",
                "multiselect" : false,
                "required" : false,
                "readonly" : false,
                "disabled" : false,
                "filterable" : true,
                "attributeId" : "a0aRN00000067pkYAA",
                "label" : "Model",
                "displaySequence" : -1,
                "hasRules" : false,
                "hidden" : false,
                "cloneable" : true,
                "isNotTranslatable" : false,
                "values" : [ {
                  "readonly" : false,
                  "disabled" : false
                } ],
                "userValues" : "Civic",
                "isNotAssetizable" : false
              }, {
                "code" : "ModelYear",
                "dataType" : "number",
                "inputType" : "number",
                "multiselect" : false,
                "required" : false,
                "readonly" : false,
                "disabled" : false,
                "filterable" : true,
                "attributeId" : "a0aRN00000067plYAA",
                "label" : "ModelYear",
                "displaySequence" : -1,
                "hasRules" : false,
                "hidden" : false,
                "cloneable" : true,
                "isNotTranslatable" : false,
                "values" : [ {
                  "readonly" : false,
                  "disabled" : false
                } ],
                "userValues" : 1998,
                "isNotAssetizable" : false
              } ]
            }
          } ]
        },
        "childProducts" : {
          "totalSize" : 2,
          "records" : [ {
            "displaySequence" : -1,
            "hasAttributes" : true,
            "productName" : "Driver",
            "ProductCode" : "Driver",
            "nat_test__RecordTypeName__c" : "InsuredPartySpec",
            "productId" : "01tRN000000LCqsYAG",
            "Name" : "BobJones",
            "instanceKey" : "BobJones",
            "currencyCode" : "USD",
            "currencySymbol" : "$",
            "hasCoverages" : true,
            "isPrimaryChild" : true,
            "attributeCategories" : {
              "totalSize" : 1,
              "records" : [ {
                "displaySequence" : 2,
                "Code__c" : "Driver",
                "Name" : "Driver",
                "id" : "a0ZRN0000009TMn2AM",
                "productAttributes" : {
                  "totalSize" : 2,
                  "records" : [ {
                    "code" : "FirstName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pmYAA",
                    "label" : "FirstName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "isNotTranslatable" : false,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Bob",
                    "isNotAssetizable" : false
                  }, {
                    "code" : "LastName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pnYAA",
                    "label" : "LastName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "isNotTranslatable" : false,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Jones",
                    "isNotAssetizable" : false
                  } ]
                }
              } ]
            }
          }, {
            "displaySequence" : -1,
            "Id" : "01tRN000000LCqsYAG",
            "Name" : "Driver",
            "productId" : "01tRN000000LCqsYAG",
            "productName" : "Driver",
            "ProductCode" : "Driver",
            "nat_test__RecordTypeName__c" : "InsuredPartySpec",
            "instanceKey" : "SarahJones",
            "attributeCategories" : {
              "totalSize" : 0,
              "records" : [ {
                "displaySequence" : -1,
                "Code__c" : "Driver",
                "Name" : "Driver",
                "id" : "a0ZRN0000009TMn2AM",
                "productAttributes" : {
                  "totalSize" : 0,
                  "records" : [ {
                    "code" : "FirstName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pmYAA",
                    "label" : "FirstName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Sarah",
                    "isNotAssetizable" : false
                  }, {
                    "code" : "LastName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pnYAA",
                    "label" : "LastName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Jones",
                    "isNotAssetizable" : false
                  } ]
                }
              } ]
            }
          } ]
        }
      }, {
        "displaySequence" : -1,
        "hasAttributes" : true,
        "productName" : "Auto",
        "ProductCode" : "Auto",
        "nat_test__RecordTypeName__c" : "InsuredItemSpec",
        "productId" : "01tRN000000LCqrYAG",
        "Name" : "1999 Toyota Camry",
        "instanceKey" : "1999 Toyota Camry",
        "currencyCode" : "USD",
        "currencySymbol" : "$",
        "hasCoverages" : true,
        "primaryParty" : {
          "instanceKey" : "MaryJones"
        },
        "otherParties" : [ {
          "instanceKey" : "BobJones"
        } ],
        "attributeCategories" : {
          "totalSize" : 1,
          "records" : [ {
            "displaySequence" : 1,
            "Code__c" : "Auto",
            "Name" : "Auto",
            "id" : "a0ZRN0000009TMm2AM",
            "productAttributes" : {
              "totalSize" : 3,
              "records" : [ {
                "code" : "Make",
                "dataType" : "text",
                "inputType" : "text",
                "multiselect" : false,
                "required" : false,
                "readonly" : false,
                "disabled" : false,
                "filterable" : true,
                "attributeId" : "a0aRN00000067pjYAA",
                "label" : "Make",
                "displaySequence" : -1,
                "hasRules" : false,
                "hidden" : false,
                "cloneable" : true,
                "isNotTranslatable" : false,
                "values" : [ {
                  "readonly" : false,
                  "disabled" : false
                } ],
                "userValues" : "Toyota",
                "isNotAssetizable" : false
              }, {
                "code" : "Model",
                "dataType" : "text",
                "inputType" : "text",
                "multiselect" : false,
                "required" : false,
                "readonly" : false,
                "disabled" : false,
                "filterable" : true,
                "attributeId" : "a0aRN00000067pkYAA",
                "label" : "Model",
                "displaySequence" : -1,
                "hasRules" : false,
                "hidden" : false,
                "cloneable" : true,
                "isNotTranslatable" : false,
                "values" : [ {
                  "readonly" : false,
                  "disabled" : false
                } ],
                "userValues" : "Camry",
                "isNotAssetizable" : false
              }, {
                "code" : "ModelYear",
                "dataType" : "number",
                "inputType" : "number",
                "multiselect" : false,
                "required" : false,
                "readonly" : false,
                "disabled" : false,
                "filterable" : true,
                "attributeId" : "a0aRN00000067plYAA",
                "label" : "ModelYear",
                "displaySequence" : -1,
                "hasRules" : false,
                "hidden" : false,
                "cloneable" : true,
                "isNotTranslatable" : false,
                "values" : [ {
                  "readonly" : false,
                  "disabled" : false
                } ],
                "userValues" : 1999,
                "isNotAssetizable" : false
              } ]
            }
          } ]
        },
        "childProducts" : {
          "totalSize" : 0,
          "records" : [ {
            "displaySequence" : -1,
            "hasAttributes" : true,
            "productName" : "Driver",
            "ProductCode" : "Driver",
            "nat_test__RecordTypeName__c" : "InsuredPartySpec",
            "productId" : "01tRN000000LCqsYAG",
            "Name" : "BobJones",
            "instanceKey" : "BobJones",
            "currencyCode" : "USD",
            "currencySymbol" : "$",
            "hasCoverages" : true,
            "isPrimaryChild" : false,
            "attributeCategories" : {
              "totalSize" : 1,
              "records" : [ {
                "displaySequence" : 2,
                "Code__c" : "Driver",
                "Name" : "Driver",
                "id" : "a0ZRN0000009TMn2AM",
                "productAttributes" : {
                  "totalSize" : 2,
                  "records" : [ {
                    "code" : "FirstName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pmYAA",
                    "label" : "FirstName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "isNotTranslatable" : false,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Bob",
                    "isNotAssetizable" : false
                  }, {
                    "code" : "LastName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pnYAA",
                    "label" : "LastName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "isNotTranslatable" : false,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Jones",
                    "isNotAssetizable" : false
                  } ]
                }
              } ]
            }
          }, {
            "displaySequence" : -1,
            "hasAttributes" : true,
            "productName" : "Driver",
            "ProductCode" : "Driver",
            "nat_test__RecordTypeName__c" : "InsuredPartySpec",
            "productId" : "01tRN000000LCqsYAG",
            "Name" : "MaryJones",
            "instanceKey" : "MaryJones",
            "currencyCode" : "USD",
            "currencySymbol" : "$",
            "hasCoverages" : true,
            "isPrimaryChild" : true,
            "attributeCategories" : {
              "totalSize" : 1,
              "records" : [ {
                "displaySequence" : 2,
                "Code__c" : "Driver",
                "Name" : "Driver",
                "id" : "a0ZRN0000009TMn2AM",
                "productAttributes" : {
                  "totalSize" : 2,
                  "records" : [ {
                    "code" : "FirstName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pmYAA",
                    "label" : "FirstName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "isNotTranslatable" : false,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Mary",
                    "isNotAssetizable" : false
                  }, {
                    "code" : "LastName",
                    "dataType" : "text",
                    "inputType" : "text",
                    "multiselect" : false,
                    "required" : false,
                    "readonly" : false,
                    "disabled" : false,
                    "filterable" : true,
                    "attributeId" : "a0aRN00000067pnYAA",
                    "label" : "LastName",
                    "displaySequence" : -1,
                    "hasRules" : false,
                    "hidden" : false,
                    "cloneable" : true,
                    "isNotTranslatable" : false,
                    "values" : [ {
                      "readonly" : false,
                      "disabled" : false
                    } ],
                    "userValues" : "Jones",
                    "isNotAssetizable" : false
                  } ]
                }
              } ]
            }
          } ]
        }
      } ]
    }
  } ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo