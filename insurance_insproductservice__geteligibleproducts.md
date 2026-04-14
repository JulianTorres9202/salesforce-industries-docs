---
title: "InsProductService:getEligibleProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__geteligibleproducts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductService:getEligibleProducts

InsProductService:getEligibleProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductService:getEligibleProducts

Use this service to find and return a list of products that match the criteria you specify.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsProductService`

Method: `getEligibleProducts`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service searches Salesforce to retrieve a set of active products that fall on or after the effective date specified. As part of the query, the service uses the criteria passed in the `filters`, `whereClause`, and `productClasses` option to get an initial set of products.
    
2.  If the products found have eligibility rules set, this service evaluates them and eliminates those that do not evaluate as eligible.
    
3.  Applies attribute filters if they're set on the remaining products found and eliminates those that are filtered out.
    
4.  If `returnProductObject` is set to `false`, returns a list of product Ids of eligible products that match the filter criteria.
    
    If `returnProductObject` is set to `true`, returns an array of product objects.
    
    In both cases, if `includeFilterAttrValues` is set to `true`, the service also returns `filterAttrValues`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`attributeFilters`

 | 

A map of `attributeCode` and values

The services returns only products that satisfy the attribute values provided in this filter.

 |
| 

`effectiveDate`

 | 

`“YYYY-MM-DD HH:MM:SS”` or `%OmniScriptDataElement%`

Defaults to today's date.

Service pulls products with an `effectiveDate` between `EffectiveDate__c` and `EndDate__c` and `IsActive`.

 |
| 

`filters`

 | 

`Product2FieldName:Value`

`Product2FieldName:%ElementName%`

Use the API name with a colon followed by either a value or a variable. For example, in an OmniScript, a variable can be a name of an element, such as an input picklist.

Separate multiple filter parameters with commas:

`ProductCode:Value,ProductCode:%ElementName%`

Filters can include any field on the `Product2` object.

 |
| 

`includeFilterAttrValues`

 | 

`true` or `false`

Defaults to `false`.

In the output JSON, along with the array of products, this adds the `filterAttrValues` object. This object contains the root product attributes marked filterable, with the possible list of values. This list is used by some UI templates to filter large sets of products.

Child product attributes are not included.

 |
| 

`lastRecordId`

 | 

Specifies the last product Id that the service pulled into the UI.

Use this option with the `pageSize` option.

 |
| 

`pageSize`

 | 

Determine how many products the service returns to the UI in one call.

 |
| 

`productClasses`

 | 

“ProductClassName1,ProductClassName2”

Comma separated list of product class names. Limits the list of products to these product classes.

 |
| 

`returnProductObject`

 | 

`true` or `false`

Defaults to

When set to `true`, the service returns an array of product objects. This response includes a list of product objects, with fields specified in the `EligibleProductFields` fieldset.

When set to `false`, the service returns a list of product Ids.

 |
| 

`searchText`

 | 

PartOfAProductName

If this option is used, the service gets only products with names that contain the value you provided.

 |
| 

`sortBy`

 | 

productField1, productField2..

Sorts the products the service gets in the order you specify.

If you don't specify a value for this option, the service sorts products returned by name in ascending alphabetical order.

 |
| 

`whereClause`

 | 

Enter any valid salesforce SOQL statement as the value for this option.

Use this option when you need to use the multi-picklist field as a filter, or you need to use any other complex filter condition that the `filters` option can't handle.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service can `userInputs` as input.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a list of product Ids. If `includeFilterAttrValues` is set to `true`, the service also returns `filterAttrValues`.

This example includes `filterAttrValues`.

```
{
  "totalNumProducts": 6,
  "effectiveDate": null,
  "inputValues": {},
  "filterAttrValues": {
    "attri2": {
      "listOfValues": [
        {
          "value": "test2",
          "displayText": "test2"
        }
      ],
      "valueDataType": "Text",
      "attributeLabel": "attri2",
      "attributeName": "attri2",
      "categoryName": "Test Attribute"
    },
    "AttntnDfctDsrdrs_Instrctn": {
      "listOfValues": [
        {
          "value": "200",
          "displayText": "200"
        }
      ],
      "valueDataType": "Percentage",
      "attributeLabel": "Instruction",
      "attributeName": "Instruction",
      "categoryName": "ADD/ADHD"
    },
    "AbaThrpyOffProf_covered_oon": {
      "listOfValues": [
        {
          "value": "100",
          "displayText": "100"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "Covered",
      "attributeName": "Covered",
      "categoryName": "ABA Therapy Office Professional"
    },
    "AddAdhd_select_oon": {
      "listOfValues": [
        {
          "value": "9999999",
          "displayText": "9999999"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "Select",
      "attributeName": "Select",
      "categoryName": "ADD/ADHD"
    },
    "AlchlSbstnceAbseInptInst_Ded_oon": {
      "listOfValues": [
        {
          "value": "null",
          "displayText": "null"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Deductible",
      "attributeName": "Deductible",
      "categoryName": "Alcohol/Substance Abuse - Inpatient Institutional"
    },
    "attri4": {
      "listOfValues": [
        {
          "value": "56",
          "displayText": "56"
        }
      ],
      "valueDataType": "Percentage",
      "attributeLabel": "attri4",
      "attributeName": "attri4",
      "categoryName": "Test Attribute"
    },
    "attri1": {
      "listOfValues": [
        {
          "value": "3000",
          "displayText": "3000"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "attri1",
      "attributeName": "attri1",
      "categoryName": "Test Attribute"
    },
    "AbaThrpyOutpProf_covered_oon": {
      "listOfValues": [
        {
          "value": "null",
          "displayText": "null"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Covered",
      "attributeName": "Covered",
      "categoryName": "ABA Therapy Outpatient Professional"
    },
    "AcupOffProf_Ded_inn": {
      "listOfValues": [
        {
          "value": "null",
          "displayText": "null"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Deductible",
      "attributeName": "Deductible",
      "categoryName": "Acupuncture Office Professional"
    },
    "COMPREHENSIVE": {
      "listOfValues": [
        {
          "value": "2019",
          "displayText": "2019"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Comprehensive",
      "attributeName": "Comprehensive",
      "categoryName": "Auto Coverage"
    },
    "amountDeductible": {
      "listOfValues": [
        {
          "value": "1000",
          "displayText": "1000"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "Property Deductible",
      "attributeName": "Property Deductible",
      "categoryName": "Coverages and Limits of Liability"
    }
  },
  "products": [
    "01t1U000000kZhdQAE",
    "01t1U000003NOvbQAG",
    "01t1U000002Jg6RQAS",
    "01t1U000003NIDIQA4",
    "01t1U000003NIDNQA4",
    "01t1U000000kZiAQAU"
  ],
  "error": "OK"
}
```

When `returnProductObject` is set to `true`, the service returns a list of products.

This example also includes filterAttrValues.

```
{
  "totalNumProducts": 6,
  "effectiveDate": null,
  "inputValues": {},
  "filterAttrValues": {
    "attri2": {
      "listOfValues": [
        {
          "value": "test2",
          "displayText": "test2"
        }
      ],
      "valueDataType": "Text",
      "attributeLabel": "attri2",
      "attributeName": "attri2",
      "categoryName": "Test Attribute"
    },
    "AttntnDfctDsrdrs_Instrctn": {
      "listOfValues": [
        {
          "value": "200",
          "displayText": "200"
        }
      ],
      "valueDataType": "Percentage",
      "attributeLabel": "Instruction",
      "attributeName": "Instruction",
      "categoryName": "ADD/ADHD"
    },
    "AbaThrpyOffProf_covered_oon": {
      "listOfValues": [
        {
          "value": "100",
          "displayText": "100"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "Covered",
      "attributeName": "Covered",
      "categoryName": "ABA Therapy Office Professional"
    },
    "AddAdhd_select_oon": {
      "listOfValues": [
        {
          "value": "9999999",
          "displayText": "9999999"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "Select",
      "attributeName": "Select",
      "categoryName": "ADD/ADHD"
    },
    "AlchlSbstnceAbseInptInst_Ded_oon": {
      "listOfValues": [
        {
          "value": "null",
          "displayText": "null"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Deductible",
      "attributeName": "Deductible",
      "categoryName": "Alcohol/Substance Abuse - Inpatient Institutional"
    },
    "attri4": {
      "listOfValues": [
        {
          "value": "56",
          "displayText": "56"
        }
      ],
      "valueDataType": "Percentage",
      "attributeLabel": "attri4",
      "attributeName": "attri4",
      "categoryName": "Test Attribute"
    },
    "attri1": {
      "listOfValues": [
        {
          "value": "3000",
          "displayText": "3000"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "attri1",
      "attributeName": "attri1",
      "categoryName": "Test Attribute"
    },
    "AbaThrpyOutpProf_covered_oon": {
      "listOfValues": [
        {
          "value": "null",
          "displayText": "null"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Covered",
      "attributeName": "Covered",
      "categoryName": "ABA Therapy Outpatient Professional"
    },
    "AcupOffProf_Ded_inn": {
      "listOfValues": [
        {
          "value": "null",
          "displayText": "null"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Deductible",
      "attributeName": "Deductible",
      "categoryName": "Acupuncture Office Professional"
    },
    "COMPREHENSIVE": {
      "listOfValues": [
        {
          "value": "2019",
          "displayText": "2019"
        }
      ],
      "valueDataType": "Number",
      "attributeLabel": "Comprehensive",
      "attributeName": "Comprehensive",
      "categoryName": "Auto Coverage"
    },
    "amountDeductible": {
      "listOfValues": [
        {
          "value": "1000",
          "displayText": "1000"
        }
      ],
      "valueDataType": "Currency",
      "attributeLabel": "Property Deductible",
      "attributeName": "Property Deductible",
      "categoryName": "Coverages and Limits of Liability"
    }
  },
  "products": [
    {
      "attributes": {
        "type": "Product2",
        "url": "/services/data/v47.0/sobjects/Product2/01t1U000000kZhdQAE"
      },
      "ProductCode": "Rent-ECO",
      "Family": "Personal Lines",
      "instest04__LineOfBusiness__c": "Property & Casualty",
      "Id": "01t1U000000kZhdQAE",
      "instest04__AttributeDefaultValues__c": "{\"amountDeductible\":1000}",
      "RecordTypeId": "0121U000000iuvEQAQ"
    },
    {
      "attributes": {
        "type": "Product2",
        "url": "/services/data/v47.0/sobjects/Product2/01t1U000003NOvbQAG"
      },
      "ProductCode": "Rent-ECOCLONEDCLONED",
      "Family": "Personal Lines",
      "instest04__LineOfBusiness__c": "Property & Casualty",
      "Id": "01t1U000003NOvbQAG",
      "instest04__AttributeDefaultValues__c": "{\"COMPREHENSIVE\":2019,\"AlchlSbstnceAbseInptInst_Ded_oon\":\"\",\"AttntnDfctDsrdrs_Instrctn\":\"200\",\"AddAdhd_select_oon\":9999999,\"AbaThrpyOffProf_covered_oon\":100,\"AbaThrpyOutpProf_covered_oon\":\"\",\"AcupOffProf_Ded_inn\":\"\",\"attri2\":\"test2\",\"attri4\":\"56\",\"attri1\":3000}",
      "RecordTypeId": "0121U000000iuvEQAQ"
    },
    {
      "attributes": {
        "type": "Product2",
        "url": "/services/data/v47.0/sobjects/Product2/01t1U000002Jg6RQAS"
      },
      "ProductCode": "Rent-ECOCLONED",
      "Family": "Personal Lines",
      "instest04__LineOfBusiness__c": "Property & Casualty",
      "Id": "01t1U000002Jg6RQAS",
      "instest04__AttributeDefaultValues__c": "{\"COMPREHENSIVE\":2019,\"AlchlSbstnceAbseInptInst_Ded_oon\":\"\",\"AttntnDfctDsrdrs_Instrctn\":\"200\",\"AddAdhd_select_oon\":9999999,\"AbaThrpyOffProf_covered_oon\":100,\"AbaThrpyOutpProf_covered_oon\":\"\",\"AcupOffProf_Ded_inn\":\"\",\"attri2\":\"test2\",\"attri4\":\"56\",\"attri1\":3000}",
      "RecordTypeId": "0121U000000iuvEQAQ"
    },
    {
      "attributes": {
        "type": "Product2",
        "url": "/services/data/v47.0/sobjects/Product2/01t1U000003NIDIQA4"
      },
      "ProductCode": "Rent-ECOCLONEDCLONEDCLONED",
      "Family": "Personal Lines",
      "instest04__LineOfBusiness__c": "Property & Casualty",
      "Id": "01t1U000003NIDIQA4",
      "instest04__AttributeDefaultValues__c": "{\"COMPREHENSIVE\":2019,\"AlchlSbstnceAbseInptInst_Ded_oon\":\"\",\"AttntnDfctDsrdrs_Instrctn\":\"200\",\"AddAdhd_select_oon\":9999999,\"AbaThrpyOffProf_covered_oon\":100,\"AbaThrpyOutpProf_covered_oon\":\"\",\"AcupOffProf_Ded_inn\":\"\",\"attri2\":\"test2\",\"attri4\":\"56\",\"attri1\":3000}",
      "RecordTypeId": "0121U000000iuvEQAQ"
    },
    {
      "attributes": {
        "type": "Product2",
        "url": "/services/data/v47.0/sobjects/Product2/01t1U000003NIDNQA4"
      },
      "ProductCode": "Rent-ECOCLONEDCLONEDCLONEDCLONED",
      "Family": "Personal Lines",
      "instest04__LineOfBusiness__c": "Property & Casualty",
      "Id": "01t1U000003NIDNQA4",
      "instest04__AttributeDefaultValues__c": "{\"COMPREHENSIVE\":2019,\"AlchlSbstnceAbseInptInst_Ded_oon\":\"\",\"AttntnDfctDsrdrs_Instrctn\":\"200\",\"AddAdhd_select_oon\":9999999,\"AbaThrpyOffProf_covered_oon\":100,\"AbaThrpyOutpProf_covered_oon\":\"\",\"AcupOffProf_Ded_inn\":\"\",\"attri2\":\"test2\",\"attri4\":\"56\",\"attri1\":3000}",
      "RecordTypeId": "0121U000000iuvEQAQ"
    },
    {
      "attributes": {
        "type": "Product2",
        "url": "/services/data/v47.0/sobjects/Product2/01t1U000000kZiAQAU"
      },
      "ProductCode": "Rent-SUPER",
      "Family": "Personal Lines",
      "instest04__LineOfBusiness__c": "Property & Casualty",
      "Id": "01t1U000000kZiAQAU",
      "instest04__AttributeDefaultValues__c": "{\"AbaThrpyOffProf_Instrctn\":null}",
      "RecordTypeId": "0121U000000iuvEQAQ"
    }
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo