---
title: "InsProductJSONService:getCoverages"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__getcoverages.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductJSONService:getCoverages

InsProductJSONService:getCoverages[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductJSONService:getCoverages

Use this service to get one or more coverages from a Product JSON using product codes.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsProductJSONService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getCoverages`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Uses the `inputKey` to identify a standard product JSON with one root product as the input JSON.
    
2.  Filter the coverages based on these remote options:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   `instanceKey`
        
    -   `productCode`
        
    -   `optionalOnly`
        
    -   `requiredOnly`
        
3.  Returns coverages filtered according to the settings in step 2.
    

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

The key the service uses to get the `productJSONResult` from the input JSON.

The default value is `inputKey`.

 |
| 

`productCode`

 | 

Returns coverages under this `productCode`. If there are multiple instances of the product, it returns coverages for all instances.

 |
| 

`instanceKey`

 | 

Returns coverages for this `instanceKey`.

 |
| 

`productCodeOnly`

 | 

`True/False`

If set to `true`, the service return the productCode for all the coverages only.

If set to `false`, the service returns the full `JSONResult` for all the coverages (including category attribute information).

 |
| 

`optionalOnly`

 | 

`True/False`

If set to `true`, returns optional coverages only.

Cannot be set to true if `requiredOnly` is set to `true`.

 |
| 

`requiredOnly`

 | 

`True/False`

If set to `true`, returns required coverages only.

Cannot be set to true if `optionalOnly` is set to `true`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service takes a typical product JSON it identifies using the `inputKey`.

To learn how product JSONs are structured, see [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.").

Here's an example of the input JSON. In this example, the `inputKey` is `configureProducts`.

```
{
        "configureProducts": {
            "totalSize": 1,
            "records": [
                {
                    "displaySequence": -1,
                    "Id": "01tf4000002SCPGAA4",
                    "Name": "Customizable Benefit Plan - PPO2",
                    "Family": "Commercial",
                    "ProductCode": "ANTM CPD PPO2",
                    "LineOfBusiness__c": "Customizable",
                    "MarketSegment__c": "Large Group",
                    "Type__c": "Medical",
                    "SubType__c": "PPO",
                    "IsRecommended__c": false,
                    "Description": "Anthem Approach 2: Coverage as Groups of Benefits, Attribute Category as Benefits, Attribute Tags (Winter'19) as INN, OON, etc. as Groups of Attributes",
                    "RecordTypeName__c": "Product",
                    "IsConfigurable__c": true,
                    "productId": "01tf4000002SCPGAA4",
                    "Price": "",
                    "attributeCategories": {
                        "totalSize": 1,
                        "records": [
                            {
                                "displaySequence": 21,
                                "Code__c": "TestAttrCat1",
                                "Name": "Test Attribute Category 1",
                                "id": "a0Of400000YCuJBEA1",
                                "productAttributes": {
                                    "totalSize": 6,
                                    "records": [
                                        {
                                            "code": "TestAttrCat1_covered_inn",
                                            "dataType": "text",
                                            "inputType": "checkbox",
                                            "multiselect": false,
                                            "required": false,
                                            "readonly": false,
                                            "disabled": false,
                                            "filterable": true,
                                            "attributeId": "a0Pf40000043qsmEAA",
                                            "label": "Covered",
                                            "displaySequence": 1,
                                            "hasRules": false,
                                            "hidden": false,
                                            "cloneable": true,
                                            "isNotTranslatable": false,
                                            "values": [
                                                {
                                                    "readonly": false,
                                                    "disabled": false
                                                }
                                            ],
                                            "userValues": true,
                                            "attributeGroupType": "In-Network"
                                        },
                                        {
                                            "code": "TestAttrCat1_covered_oon",
                                            "dataType": "text",
                                            "inputType": "checkbox",
                                            "multiselect": false,
                                            "required": false,
                                            "readonly": false,
                                            "disabled": false,
                                            "filterable": true,
                                            "attributeId": "a0Pf40000043qsrEAA",
                                            "label": "Covered",
                                            "displaySequence": 2,
                                            "hasRules": false,
                                            "hidden": false,
                                            "cloneable": true,
                                            "isNotTranslatable": false,
                                            "values": [
                                                {
                                                    "readonly": false,
                                                    "disabled": false
                                                }
                                            ],
                                            "userValues": true,
                                            "attributeGroupType": "Out-Of-Network"
                                        },
                                        {
                                            "code": "TestAttrCat1_attr1",
                                            "dataType": "text",
                                            "inputType": "dropdown",
                                            "multiselect": false,
                                            "required": false,
                                            "readonly": false,
                                            "disabled": false,
                                            "filterable": true,
                                            "attributeId": "a0Pf40000043qswEAA",
                                            "label": "Test Attribute 1",
                                            "displaySequence": 5,
                                            "hasRules": false,
                                            "hidden": false,
                                            "cloneable": true,
                                            "isNotTranslatable": false,
                                            "values": [
                                                {
                                                    "id": "0",
                                                    "label": "Value One",
                                                    "readonly": false,
                                                    "disabled": false,
                                                    "value": "val1"
                                                },
                                                {
                                                    "id": "1",
                                                    "label": "Value Two",
                                                    "readonly": false,
                                                    "disabled": false,
                                                    "value": "val2"
                                                },
                                                {
                                                    "id": "2",
                                                    "label": "Value Three",
                                                    "readonly": false,
                                                    "disabled": false,
                                                    "value": "val3"
                                                }
                                            ],
                                            "userValues": "val2"
                                        },
                                        {
                                            "code": "TestAttrCat1_attr2",
                                            "dataType": "text",
                                            "inputType": "checkbox",
                                            "multiselect": true,
                                            "required": false,
                                            "readonly": false,
                                            "disabled": false,
                                            "filterable": true,
                                            "attributeId": "a0Pf40000043qtuEAA",
                                            "label": "Test Attribute 2",
                                            "displaySequence": 6,
                                            "hasRules": false,
                                            "hidden": false,
                                            "cloneable": true,
                                            "isNotTranslatable": false,
                                            "values": [
                                                {
                                                    "id": "0",
                                                    "label": "Message One",
                                                    "readonly": false,
                                                    "disabled": false,
                                                    "value": "msg1"
                                                },
                                                {
                                                    "id": "1",
                                                    "label": "Message Two",
                                                    "readonly": false,
                                                    "disabled": false,
                                                    "value": "msg2"
                                                },
                                                {
                                                    "id": "2",
                                                    "label": "Message Three",
                                                    "readonly": false,
                                                    "disabled": false,
                                                    "value": "msg3"
                                                }
                                            ],
                                            "userValues": [
                                                {
                                                    "msg1": false
                                                },
                                                {
                                                    "msg2": true
                                                },
                                                {
                                                    "msg3": false
                                                }
                                            ]
                                        },
                                        {
                                            "code": "TestAttrCat1_attr10_inn",
                                            "dataType": "number",
                                            "inputType": "number",
                                            "multiselect": false,
                                            "required": false,
                                            "readonly": false,
                                            "disabled": false,
                                            "filterable": true,
                                            "attributeId": "a0Pf40000043qt6EAA",
                                            "label": "Test Attribute 10",
                                            "displaySequence": 10,
                                            "hasRules": false,
                                            "hidden": false,
                                            "cloneable": true,
                                            "isNotTranslatable": false,
                                            "values": [
                                                {
                                                    "readonly": false,
                                                    "disabled": false
                                                }
                                            ],
                                            "userValues": 10,
                                            "attributeGroupType": "In-Network"
                                        },
                                        {
                                            "code": "TestAttrCat1_attr10_oon",
                                            "dataType": "number",
                                            "inputType": "number",
                                            "multiselect": false,
                                            "required": false,
                                            "readonly": false,
                                            "disabled": false,
                                            "filterable": true,
                                            "attributeId": "a0Pf40000043qtGEAQ",
                                            "label": "Test Attribute 10",
                                            "displaySequence": 20,
                                            "hasRules": false,
                                            "hidden": false,
                                            "cloneable": true,
                                            "isNotTranslatable": false,
                                            "values": [
                                                {
                                                    "readonly": false,
                                                    "disabled": false
                                                }
                                            ],
                                            "userValues": 10,
                                            "attributeGroupType": "Out-Of-Network"
                                        }
                                    ]
                                }
                            }
                        ]
                    },
                    "childProducts": {
                        "totalSize": 5,
                        "records": [
                            {
                                "displaySequence": 3,
                                "Id": "01tf4000002TgTLAA0",
                                "Name": "Preventive Care Benefits",
                                "ProductCode": "ANTM_Preventive",
                                "LineOfBusiness__c": "Group Health",
                                "MarketSegment__c": "Large Group",
                                "Type__c": "Medical",
                                "SubType__c": "PPO",
                                "IsRecommended__c": false,
                                "RecordTypeName__c": "CoverageSpec",
                                "IsConfigurable__c": true,
                                "productId": "01tf4000002TgTLAA0",
                                "pciId": "a2pf4000000ksHbAAI",
                                "isOptional": true,
                                "isSelected": false,
                                "attributeCategories": {
                                    "totalSize": 2,
                                    "records": [
                                        {
                                            "displaySequence": 121,
                                            "Code__c": "ExamRoutAdulPhys",
                                            "Name": "Exam - Routine Adult Physical",
                                            "id": "a0Of400000YCIFyEAP",
                                            "productAttributes": {
                                                "totalSize": 9,
                                                "records": [
                                                    {
                                                        "code": "ExamRoutAdulPhys_covered_inn",
                                                        "dataType": "text",
                                                        "inputType": "checkbox",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzQiEAK",
                                                        "label": "Covered",
                                                        "displaySequence": 1,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": true,
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamRoutAdulPhys_covered_oon",
                                                        "dataType": "text",
                                                        "inputType": "checkbox",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzQxEAK",
                                                        "label": "Covered",
                                                        "displaySequence": 2,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": true,
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "ExamRoutAdulPhys_coinsuranc_inn",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzRMEA0",
                                                        "label": "Covered at",
                                                        "displaySequence": 3,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "100%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "100"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "95%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "95"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "90%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "90"
                                                            }
                                                        ],
                                                        "userValues": "100",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamRoutAdulPhys_coinsurance_oon",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzRWEA0",
                                                        "label": "Covered at",
                                                        "displaySequence": 4,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "100%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "100"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "95%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "95"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "90%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "90"
                                                            }
                                                        ],
                                                        "userValues": "95",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "ExamRoutAdulPhys_deductible_inn",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzhnEAC",
                                                        "label": "Deductible",
                                                        "displaySequence": 5,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "Yes",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "yes"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "No",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "no"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "N/A",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "n/a"
                                                            }
                                                        ],
                                                        "userValues": "no",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamRoutAdulPhys_deductible_oon",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzhxEAC",
                                                        "label": "Deductible",
                                                        "displaySequence": 6,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "Yes",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "yes"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "No",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "no"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "N/A",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "n/a"
                                                            }
                                                        ],
                                                        "userValues": "yes",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "ExamRoutAdulPhys_copay_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mzi2EAC",
                                                        "label": "Copay ($)",
                                                        "displaySequence": 7,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamRoutAdulPhys_copay_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mzi7EAC",
                                                        "label": "Copay ($)",
                                                        "displaySequence": 8,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "ExamPoutAdulPhys_msg1",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": true,
                                                        "disabled": true,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mzj5EAC",
                                                        "label": "don't show this label",
                                                        "displaySequence": 9,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": true,
                                                                "disabled": true
                                                            }
                                                        ],
                                                        "userValues": "Includes routine gynecological exams"
                                                    }
                                                ]
                                            }
                                        },
                                        {
                                            "displaySequence": 122,
                                            "Code__c": "ExamWellChilCare",
                                            "Name": "Exam - Well Child Care",
                                            "id": "a0Of400000YCId5EAH",
                                            "productAttributes": {
                                                "totalSize": 8,
                                                "records": [
                                                    {
                                                        "code": "ExamWellChilCare_covered_inn",
                                                        "dataType": "text",
                                                        "inputType": "checkbox",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MziHEAS",
                                                        "label": "Covered",
                                                        "displaySequence": 1,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": true,
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamWellChilCare_covered_oon",
                                                        "dataType": "text",
                                                        "inputType": "checkbox",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MziMEAS",
                                                        "label": "Covered",
                                                        "displaySequence": 2,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": true,
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "ExamWellChilCare_coinsurance_inn",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MziREAS",
                                                        "label": "Covered at",
                                                        "displaySequence": 3,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "100%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "100"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "95%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "95"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "90%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "90"
                                                            }
                                                        ],
                                                        "userValues": "100",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamWellChilCare_coinsurance_oon",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MziWEAS",
                                                        "label": "Covered at",
                                                        "displaySequence": 4,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "100%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "100"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "95%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "95"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "90%",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "90"
                                                            }
                                                        ],
                                                        "userValues": "95",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "ExamWellChilCare_deductible_inn",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzibEAC",
                                                        "label": "Deductible",
                                                        "displaySequence": 5,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "Yes",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "yes"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "No",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "no"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "N/A",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "n/a"
                                                            }
                                                        ],
                                                        "userValues": "no",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamWellChilCare_deductible_oon",
                                                        "dataType": "text",
                                                        "inputType": "dropdown",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzigEAC",
                                                        "label": "Deductible",
                                                        "displaySequence": 6,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "id": "0",
                                                                "label": "Yes",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "yes"
                                                            },
                                                            {
                                                                "id": "1",
                                                                "label": "No",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "no"
                                                            },
                                                            {
                                                                "id": "2",
                                                                "label": "N/A",
                                                                "readonly": false,
                                                                "disabled": false,
                                                                "value": "n/a"
                                                            }
                                                        ],
                                                        "userValues": "yes",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "ExamWellChilCare_copay_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzilEAC",
                                                        "label": "Copay ($)",
                                                        "displaySequence": 7,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "description": "USD",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "ExamWellChilCare_copay_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MzivEAC",
                                                        "label": "Copay ($)",
                                                        "displaySequence": 8,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "description": "USD",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    }
                                                ]
                                            }
                                        }
                                    ]
                                }
                            },
                            {
                                "displaySequence": 4,
                                "Id": "01tf4000002TZV2AAO",
                                "Name": "General Benefits",
                                "ProductCode": "ANTM_Gen_Ben",
                                "Type__c": "Medical",
                                "IsRecommended__c": false,
                                "RecordTypeName__c": "CoverageSpec",
                                "IsConfigurable__c": true,
                                "productId": "01tf4000002TZV2AAO",
                                "pciId": "a2pf4000000kt6gAAA",
                                "isOptional": false,
                                "isSelected": true,
                                "attributeCategories": {
                                    "totalSize": 2,
                                    "records": [
                                        {
                                            "displaySequence": 80,
                                            "Code__c": "ANTM_Deductible",
                                            "Name": "Deductible",
                                            "id": "a0Of400000YC9KiEAL",
                                            "productAttributes": {
                                                "totalSize": 22,
                                                "records": [
                                                    {
                                                        "code": "Deductible_covered_inn",
                                                        "dataType": "text",
                                                        "inputType": "checkbox",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003N0PtEAK",
                                                        "label": "Covered",
                                                        "displaySequence": 1,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": true,
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_covered_oon",
                                                        "dataType": "text",
                                                        "inputType": "checkbox",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003N0Q8EAK",
                                                        "label": "Covered",
                                                        "displaySequence": 2,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": true,
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_individual_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MpbMEAS",
                                                        "label": "Individual",
                                                        "displaySequence": 10,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "$500",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_1_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MpcFEAS",
                                                        "label": "Employee +1",
                                                        "displaySequence": 20,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_spouse_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MpcPEAS",
                                                        "label": "Employee + Spouse",
                                                        "displaySequence": 30,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_child_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MpceEAC",
                                                        "label": "Employee + Child",
                                                        "displaySequence": 40,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_children_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mpd3EAC",
                                                        "label": "Employee + Children",
                                                        "displaySequence": 50,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_family_inn",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MpdDEAS",
                                                        "label": "Family",
                                                        "displaySequence": 60,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "$1,500",
                                                        "attributeGroupType": "In-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_individual_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MpdSEAS",
                                                        "label": "Individual",
                                                        "displaySequence": 70,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "$1,500",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_1_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003MpdmEAC",
                                                        "label": "Employee +1",
                                                        "displaySequence": 80,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_spouse_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mq7GEAS",
                                                        "label": "Employee + Spouse",
                                                        "displaySequence": 90,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_child_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mq7VEAS",
                                                        "label": "Employee + Child",
                                                        "displaySequence": 100,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_children_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mq7fEAC",
                                                        "label": "Employee + Children",
                                                        "displaySequence": 110,
                                                        "hasRules": false,
                                                        "hidden": false,
                                                        "cloneable": true,
                                                        "isNotTranslatable": false,
                                                        "values": [
                                                            {
                                                                "readonly": false,
                                                                "disabled": false
                                                            }
                                                        ],
                                                        "userValues": "N/A",
                                                        "attributeGroupType": "Out-Of-Network"
                                                    },
                                                    {
                                                        "code": "Deductible_ee_family_oon",
                                                        "dataType": "text",
                                                        "inputType": "text",
                                                        "multiselect": false,
                                                        "required": false,
                                                        "readonly": false,
                                                        "disabled": false,
                                                        "filterable": true,
                                                        "attributeId": "a0Pf4000003Mq84EAC",
                                                        "label": "Family",
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the list of coverages under the `coverages` key.

```
{
	"coverages": [{
		"displaySequence": 1,
		"Price": "",
		"Id": "01tf40000011PFdAAM",
		"Name": "Accelerated Benefit Rider",
		"Description": "An accelerated death benefit (ADB) is a benefit that can be attached to a life insurance policy that enables the policyholder to receive cash advances against the death benefit in the case of being diagnosed with a terminal illness.",
		"Family": "Individual Life",
		"ProductCode": "ABR",
		"LineOfBusiness__c": "Individual Life",
		"Type__c": "Coverages",
		"IsRecommended__c": false,
		"RecordTypeName__c": "CoverageSpec",
		"IsConfigurable__c": true,
		"productId": "01tf40000011PFdAAM",
		"pciId": "a2mf4000000kag4AAA",
		"isOptional": false,
		"isSelected": true,
		"parentInstanceKey": "Jack Kirkland",
		"pathFromRoot": "[0].childProducts.records[0].childProducts.records[3]",
		"formattedParentInstanceKey": "jack-kirkland",
		"parentProductName": "Jack Kirkland",
		"originalIndex": 3,
		"numberCategories": 12,
		"numberAttributes": 18,
		"popoverOpen": false,
		"rootProductCode": "ABR",
		"rootProductId": "a2mf4000000kag4AAA",
		"cached": true,
		"attributeCategories": {
			"totalSize": 2,
			"records": [{
					"displaySequence": 1331,
					"Code__c": "MAX",
					"Name": "Maximums",
					"id": "a08f4000007go2XAAQ",
					"productAttributes": {
						"totalSize": 1,
						"records": [{
							"code": "ATTRIBUTE-074",
							"dataType": "currency",
							"inputType": "number",
							"required": false,
							"readonly": false,
							"disabled": false,
							"filterable": true,
							"attributeId": "a09f4000002hYrqAAE",
							"label": "Lifetime Maximum",
							"displaySequence": 5,
							"hasRules": true,
							"hidden": false,
							"values": [{
								"readonly": false,
								"disabled": false
							}],
							"userValues": 1200000,
							"parentProductCode": "ABR",
							"pathFromRoot": "childProducts.records[3].attributeCategories.records[0].productAttributes.records[0]",
							"pathFromChild": "attributeCategories.records[0].productAttributes.records[0]",
							"originalProductIndex": 3,
							"originalCategoryIndex": 0,
							"originalAttributeIndex": 0,
							"parentProductId": "a2mf4000000kag4AAA",
							"setValueRuleCount": 4,
							"originalUserValues": 1200000,
							"ruleSetValue": false,
							"rules": [{
									"ruleType": "Set Value",
									"expression": " == 500000",
									"valueExpression": "1200000",
									"actions": {
										"Set Value": {
											"rest": {
												"params": {},
												"method": null,
												"link": null
											},
											"remote": {
												"params": {}
											},
											"client": {
												"params": {}
											}
										}
									},
									"counted": true,
									"calculatedValueExpression": 1200000,
									"ruleEvaluation": true
								},
								{
									"ruleType": "Set Value",
									"expression": " == 2000000",
									"valueExpression": "1999999",
									"actions": {
										"Set Value": {
											"rest": {
												"params": {},
												"method": null,
												"link": null
											},
											"remote": {
												"params": {}
											},
											"client": {
												"params": {}
											}
										}
									},
									"counted": true,
									"ruleEvaluation": false
								}
							]
						}]
					}
				},
				{
					...
				}
			]
		},
		"lastNonOptional": true,
		"showTypeHeader": true
	}],
	"error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo