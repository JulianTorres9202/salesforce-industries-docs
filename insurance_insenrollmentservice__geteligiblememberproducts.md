---
title: "InsEnrollmentService:getEligibleMemberProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__geteligiblememberproducts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService:getEligibleMemberProducts

InsEnrollmentService:getEligibleMemberProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService:getEligibleMemberProducts

Use this service to return eligible products for members of a census and groups them by type.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsEnrollmentService`

Method: `getEligibleMemberProducts`

[](https://help.salesforce.com/s?language=en_US)

## How It works

1.  This service takes a `contractId` and looks for information from the `GroupCensus__c` attached to it.
    
2.  Using the `GroupCensus__c` obtained from the contractId, the service retrieves all primary `GroupCensusMembers__c` and their dependents.
    
3.  The `censusRatingFact` is created using the `GroupCensus__c` Product Code and the `AttributeSelectedValues__c.`
    
4.  The `contractId` and `categories` options are used to retrieve the `ContractLineItem__c` (Plans) and associated metadata.
    
5.  The primary `GroupCensusMembers__c` uses the `censusRatingFact` and the `AttributeSelectedValues__c` of the primary member, and its dependents, to check the eligibility of a primary member.
    
6.  For each `ContractLineItem__c`  on the contract, its `EligibilityCriteria__c`  will be compared to the each of the primary member's inputs, from above.
    
    If a member has eligible products, the service will attach the primary member, sort it by category, then add it to the output JSON. Members with no eligible products will not be added to the output JSON.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`contractId`

 | 

Required.

Id of the contract.

 |
| 

`category`

 | 

Optional string.

Comma separated list of categories (Medical, Dental, Vision).

Will return plans only for specified categories.

Default = all categories.

 |
| 

`onlyWhenMultiplePlansAvailable`

 | 

Optional.

Boolean.

True returns options only when multiple plans are available.

Used to display members with their available options for each category, so user can make selections.

 |
| 

`onlyWhenSinglePlansAvailable`

 | 

Optional.

Boolean.

True returns options only when single plans are available.

Used for auto-enrollment when members have only a single plan option.

 |
| 

`omitChildProducts`

 | 

Boolean.

If `true`, only root products are returned.

Default = `false`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON is a list of census members, with First Name, Last Name, Census Member Id, Categories of Products that they are eligible for.

```
{
  "contractId": "8006F0000014asaQAA",
  "ContextId": "",
  "timeStamp": "2019-08-30T08:34:43.150Z",
  "userId": "0056F0000077bTYQAY",
  "userName": "john@company.com",
  "userProfile": "System Administrator",
  "userTimeZone": -420,
  "userCurrencyCode": "EUR",
  "sfdcIFrameOrigin": "https://company.com",
  "sfdcIFrameHost": "web",
  "layout": "lightning",
  "isdtp": "p1",
  "id": "a1e6F000004RxxkQAC",
  "vlcPersistentComponent": {},
  "totalSize": 0,
  "records": [
    {
      "displaySequence": -1,
      "Id": "a386F000001ao9xQAA",
      "FirstName": "Lynn",
      "LastName": "Robbins",
      "Medical": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F00000AyW3ZQAV",
            "planId": "a1u6F000005ipRCQAY",
            "productName": "Acupuncture Office Professional",
            "Type": "Medical",
            "Description": "Anthem",
            "ProductCode": "AcupOffiProf",
            "MarketSegment": "Large Group",
            "LineOfBusiness": "Group Health",
            "attributeCategories": {
              "totalSize": 2,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1XLUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "INN_covered"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1XMUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "dropdown",
                        "dataType": "text",
                        "code": "INN_deductible"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1XNUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "INN_copay"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 5,
                        "label": "IN covered",
                        "attributeId": "a1R6F00000Km1XKUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "INNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6uJUAT",
                  "Name": "In-Network",
                  "Code__c": "Vlocity_INN",
                  "displaySequence": 210
                },
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1ZGUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "OON_covered"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1ZHUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "radio",
                        "dataType": "text",
                        "code": "OON_deductible"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1ZIUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "OON_copay"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 4,
                        "label": "ON Covered",
                        "attributeId": "a1R6F00000Km1ZFUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "OutNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6vIUAT",
                  "Name": "Out-Of-Network",
                  "Code__c": "ANTM_OON",
                  "displaySequence": 220
                }
              ]
            }
          }
        ]
      },
      "Dental": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F000007sPVlQAM",
            "planId": "a1u6F000005j7AlQAI",
            "productName": "Dental 2",
            "Type": "Dental",
            "ProductCode": "DENTAL2",
            "attributeCategories": {
              "totalSize": 1,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Office Visits & Exams",
                        "attributeId": "a1R6F00000K0X4sUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILLNESS"
                      },
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Unexpected Illness",
                        "attributeId": "a1R6F00000K0X4tUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILL-UNEXPECTED"
                      }
                    ],
                    "totalSize": 2
                  },
                  "id": "a1Q6F000009NzKhUAK",
                  "Name": "Benefit",
                  "Code__c": "BENEFIT",
                  "displaySequence": 483
                }
              ]
            }
          }
        ]
      }
    },
    {
      "displaySequence": -1,
      "Id": "a386F000001aoA0QAI",
      "FirstName": "Mara",
      "LastName": "Robbins",
      "Medical": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F00000AyW3ZQAV",
            "planId": "a1u6F000005ipRCQAY",
            "productName": "Acupuncture Office Professional",
            "Type": "Medical",
            "Description": "Anthem",
            "ProductCode": "AcupOffiProf",
            "MarketSegment": "Large Group",
            "LineOfBusiness": "Group Health",
            "attributeCategories": {
              "totalSize": 2,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1XLUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "INN_covered"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1XMUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "dropdown",
                        "dataType": "text",
                        "code": "INN_deductible"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1XNUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "INN_copay"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 5,
                        "label": "IN covered",
                        "attributeId": "a1R6F00000Km1XKUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "INNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6uJUAT",
                  "Name": "In-Network",
                  "Code__c": "Vlocity_INN",
                  "displaySequence": 210
                },
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1ZGUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "OON_covered"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1ZHUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "radio",
                        "dataType": "text",
                        "code": "OON_deductible"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1ZIUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "OON_copay"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 4,
                        "label": "ON Covered",
                        "attributeId": "a1R6F00000Km1ZFUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "OutNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6vIUAT",
                  "Name": "Out-Of-Network",
                  "Code__c": "ANTM_OON",
                  "displaySequence": 220
                }
              ]
            }
          }
        ]
      },
      "Dental": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F000007sPVlQAM",
            "planId": "a1u6F000005j7AlQAI",
            "productName": "Dental 2",
            "Type": "Dental",
            "ProductCode": "DENTAL2",
            "attributeCategories": {
              "totalSize": 1,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Office Visits & Exams",
                        "attributeId": "a1R6F00000K0X4sUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILLNESS"
                      },
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Unexpected Illness",
                        "attributeId": "a1R6F00000K0X4tUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILL-UNEXPECTED"
                      }
                    ],
                    "totalSize": 2
                  },
                  "id": "a1Q6F000009NzKhUAK",
                  "Name": "Benefit",
                  "Code__c": "BENEFIT",
                  "displaySequence": 483
                }
              ]
            }
          }
        ]
      }
    },
    {
      "displaySequence": -1,
      "Id": "a386F000001ao9yQAA",
      "FirstName": "Bill",
      "LastName": "William",
      "Medical": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F00000AyW3ZQAV",
            "planId": "a1u6F000005ipRCQAY",
            "productName": "Acupuncture Office Professional",
            "Type": "Medical",
            "Description": "Anthem",
            "ProductCode": "AcupOffiProf",
            "MarketSegment": "Large Group",
            "LineOfBusiness": "Group Health",
            "attributeCategories": {
              "totalSize": 2,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1XLUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "INN_covered"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1XMUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "dropdown",
                        "dataType": "text",
                        "code": "INN_deductible"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1XNUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "INN_copay"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 5,
                        "label": "IN covered",
                        "attributeId": "a1R6F00000Km1XKUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "INNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6uJUAT",
                  "Name": "In-Network",
                  "Code__c": "Vlocity_INN",
                  "displaySequence": 210
                },
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1ZGUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "OON_covered"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1ZHUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "radio",
                        "dataType": "text",
                        "code": "OON_deductible"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1ZIUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "OON_copay"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 4,
                        "label": "ON Covered",
                        "attributeId": "a1R6F00000Km1ZFUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "OutNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6vIUAT",
                  "Name": "Out-Of-Network",
                  "Code__c": "ANTM_OON",
                  "displaySequence": 220
                }
              ]
            }
          }
        ]
      },
      "Dental": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F000007sPVlQAM",
            "planId": "a1u6F000005j7AlQAI",
            "productName": "Dental 2",
            "Type": "Dental",
            "ProductCode": "DENTAL2",
            "attributeCategories": {
              "totalSize": 1,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Office Visits & Exams",
                        "attributeId": "a1R6F00000K0X4sUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILLNESS"
                      },
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Unexpected Illness",
                        "attributeId": "a1R6F00000K0X4tUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILL-UNEXPECTED"
                      }
                    ],
                    "totalSize": 2
                  },
                  "id": "a1Q6F000009NzKhUAK",
                  "Name": "Benefit",
                  "Code__c": "BENEFIT",
                  "displaySequence": 483
                }
              ]
            }
          }
        ]
      }
    },
    {
      "displaySequence": -1,
      "Id": "a386F000001ao9zQAA",
      "FirstName": "Bob",
      "LastName": "Jason",
      "Medical": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F00000AyW3ZQAV",
            "planId": "a1u6F000005ipRCQAY",
            "productName": "Acupuncture Office Professional",
            "Type": "Medical",
            "Description": "Anthem",
            "ProductCode": "AcupOffiProf",
            "MarketSegment": "Large Group",
            "LineOfBusiness": "Group Health",
            "attributeCategories": {
              "totalSize": 2,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1XLUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "INN_covered"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1XMUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "dropdown",
                        "dataType": "text",
                        "code": "INN_deductible"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1XNUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "INN_copay"
                      },
                      {
                        "attributeGroupType": "In-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 5,
                        "label": "IN covered",
                        "attributeId": "a1R6F00000Km1XKUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "INNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6uJUAT",
                  "Name": "In-Network",
                  "Code__c": "Vlocity_INN",
                  "displaySequence": 210
                },
                {
                  "productAttributes": {
                    "records": [
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Covered at",
                        "attributeId": "a1R6F00000Km1ZGUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "percentage",
                        "code": "OON_covered"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Deductible",
                        "attributeId": "a1R6F00000Km1ZHUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "radio",
                        "dataType": "text",
                        "code": "OON_deductible"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 3,
                        "label": "Copay",
                        "attributeId": "a1R6F00000Km1ZIUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "OON_copay"
                      },
                      {
                        "attributeGroupType": "Out-Of-Network",
                        "userValues": null,
                        "values": [
                          {
                            "disabled": false,
                            "readonly": false
                          }
                        ],
                        "isNotTranslatable": false,
                        "cloneable": true,
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 4,
                        "label": "ON Covered",
                        "attributeId": "a1R6F00000Km1ZFUAZ",
                        "filterable": true,
                        "disabled": false,
                        "readonly": false,
                        "required": false,
                        "multiselect": false,
                        "inputType": "checkbox",
                        "dataType": "text",
                        "code": "OutNetwork_covered"
                      }
                    ],
                    "totalSize": 4
                  },
                  "id": "a1Q6F00000FR6vIUAT",
                  "Name": "Out-Of-Network",
                  "Code__c": "ANTM_OON",
                  "displaySequence": 220
                }
              ]
            }
          }
        ]
      },
      "Dental": {
        "totalSize": 1,
        "records": [
          {
            "displaySequence": -1,
            "Id": "01t6F000007sPVlQAM",
            "planId": "a1u6F000005j7AlQAI",
            "productName": "Dental 2",
            "Type": "Dental",
            "ProductCode": "DENTAL2",
            "attributeCategories": {
              "totalSize": 1,
              "records": [
                {
                  "productAttributes": {
                    "records": [
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 1,
                        "label": "Office Visits & Exams",
                        "attributeId": "a1R6F00000K0X4sUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILLNESS"
                      },
                      {
                        "userValues": null,
                        "values": [
                          {
                            "disabled": true,
                            "readonly": true
                          }
                        ],
                        "hidden": false,
                        "hasRules": false,
                        "displaySequence": 2,
                        "label": "Unexpected Illness",
                        "attributeId": "a1R6F00000K0X4tUAF",
                        "filterable": true,
                        "disabled": false,
                        "readonly": true,
                        "required": false,
                        "inputType": "number",
                        "dataType": "currency",
                        "code": "ILL-UNEXPECTED"
                      }
                    ],
                    "totalSize": 2
                  },
                  "id": "a1Q6F000009NzKhUAK",
                  "Name": "Benefit",
                  "Code__c": "BENEFIT",
                  "displaySequence": 483
                }
              ]
            }
          }
        ]
      }
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo