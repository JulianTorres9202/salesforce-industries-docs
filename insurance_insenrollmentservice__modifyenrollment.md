---
title: "InsEnrollmentService:modifyEnrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__modifyenrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService:modifyEnrollment

. InsEnrollmentService:modifyEnrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService:modifyEnrollment

Use this service to modify the enrollments, dependents, and coverages of each enrollment for input members. You can use this service to add new or remove existing plans or add or remove dependents.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsEnrollmentService`

Method: `modifyEnrollment`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Query for Group Census Members, either all members of a given `censusID`, or only members specified in `censusMemberIds` list.
    
2.  Search for related pre-enrolled plans linked to each member by Group Census Member Plan.
    
3.  For each member, retrieve the plan's product, and check eligibility.
    
4.  If product is eligible, create the Policy object.
    
5.  To remove an enrollment, an additional entry  "deletePolicies" within the member details will contain a list of policy IDs to delete. If this is not present, it is assumed that the policy is for modification.
    
6.  To remove a dependent, an additional entry `"isDeleted"` : true exists in the dependents details within an enrollment.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`records`

 | 

Required.

The enrollments list to be modified for the member.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here is a sample input JSON for `censusId`:

| 
Environment

 | 

pm\_testing\_daily@vlocity.com

 |
| --- | --- |
| 

Card to simulate testing

 | 

pm\_testing\_daily modify enrollment OS

 |

-   The input for this service has a format similar to the output for `InsEnrollmentService.getMemberEnrollments`.
    

```
{
  "records": {
    "displaySequence": -1,
    "First Name": "Allan",
    "Last Name": "Border",
    "Id": "a472E000001IH6tQAG",
    "contactId": "0032E00002Znpm3QAB",
    "deletePolicies": [
      {
        "Id": "02i2E00000GGExPQAX"
      }
    ],
    "enrollments": {
      "totalSize": 4,
      "records": [
        {
          "displaySequence": -1,
          "Id": "02i2E00000GGExPQAX",
          "productId": "01t2E00000Ne5usQAB",
          "accountId": "0012E0000232F9XQAU",
          "primaryMemberContactId": "0032E00002Znpm3QAB",
          "productName": "Vlocity SG - Medical Plan PPO 35",
          "Name": "Vlocity SG - Medical Plan PPO 35",
          "EffectiveStart": "2019-09-12",
          "EffectiveEnd": "2020-09-11",
          "Price": 3000,
          "planId": "a2N2E000003trGMUAY",
          "contractId": "8002E000003lsR6QAI",
          "ProductCode": "SG-PPO-35-GC",
          "RecordTypeName__c": "Product",
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
                          "disabled": true,
                          "readonly": true
                        }
                      ],
                      "isNotTranslatable": false,
                      "cloneable": true,
                      "hidden": false,
                      "hasRules": false,
                      "displaySequence": 3,
                      "label": "Deductible",
                      "attributeId": "a092E00000W3ATfQAN",
                      "filterable": true,
                      "disabled": true,
                      "readonly": true,
                      "required": false,
                      "multiselect": false,
                      "inputType": "text",
                      "dataType": "text",
                      "code": "SG_annualDed_INN"
                    },
                    {
                      "attributeGroupType": "In-Network",
                      "userValues": null,
                      "values": [
                        {
                          "disabled": true,
                          "readonly": true
                        }
                      ],
                      "isNotTranslatable": false,
                      "cloneable": true,
                      "hidden": false,
                      "hasRules": false,
                      "displaySequence": 4,
                      "label": "Out Of Pocket",
                      "attributeId": "a092E00000W3AThQAN",
                      "filterable": true,
                      "disabled": true,
                      "readonly": true,
                      "required": false,
                      "multiselect": false,
                      "inputType": "text",
                      "dataType": "text",
                      "code": "SG_annualOOP_INN"
                    },
                    {
                      "attributeGroupType": "In-Network",
                      "userValues": null,
                      "values": [
                        {
                          "disabled": true,
                          "readonly": true
                        }
                      ],
                      "isNotTranslatable": false,
                      "cloneable": true,
                      "hidden": false,
                      "hasRules": false,
                      "displaySequence": 5,
                      "label": "Coinsurance",
                      "attributeId": "a092E00000W3ATjQAN",
                      "filterable": true,
                      "disabled": true,
                      "readonly": true,
                      "required": false,
                      "multiselect": false,
                      "inputType": "text",
                      "dataType": "text",
                      "code": "SG_coinsurance_INN"
                    },
                    {
                      "attributeGroupType": "In-Network",
                      "userValues": null,
                      "values": [
                        {
                          "disabled": true,
                          "readonly": true
                        }
                      ],
                      "isNotTranslatable": false,
                      "cloneable": true,
                      "hidden": false,
                      "hasRules": false,
                      "displaySequence": 6,
                      "label": "Office Visit",
                      "attributeId": "a092E00000W3AUBQA3",
                      "filterable": true,
                      "disabled": true,
                      "readonly": true,
                      "required": false,
                      "multiselect": false,
                      "inputType": "text",
                      "dataType": "text",
                      "code": "SG_primaryCare_INN"
                    }
                  ],
                  "totalSize": 4
                },
                "id": "a082E00000XTXs4QAH",
                "Name": "SG Medical",
                "Code__c": "SG_Medical",
                "displaySequence": 2000
              },
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
                      "isNotTranslatable": false,
                      "cloneable": true,
                      "hidden": true,
                      "hasRules": false,
                      "displaySequence": 0,
                      "label": "Product Code",
                      "attributeId": "a092E00000W3AS0QAN",
                      "filterable": false,
                      "disabled": true,
                      "readonly": true,
                      "required": false,
                      "multiselect": false,
                      "inputType": "text",
                      "dataType": "text",
                      "code": "SG_ProductCode"
                    },
                    {
                      "userValues": null,
                      "values": [
                        {
                          "disabled": true,
                          "readonly": true
                        }
                      ],
                      "isNotTranslatable": false,
                      "cloneable": true,
                      "hidden": true,
                      "hasRules": false,
                      "displaySequence": 1,
                      "label": "Product Name",
                      "attributeId": "a092E00000W3ARyQAN",
                      "filterable": false,
                      "disabled": true,
                      "readonly": true,
                      "required": false,
                      "multiselect": false,
                      "inputType": "text",
                      "dataType": "text",
                      "code": "SG_ProductName"
                    },
                    {
                      "userValues": null,
                      "values": [
                        {
                          "disabled": true,
                          "readonly": true
                        }
                      ],
                      "isNotTranslatable": false,
                      "cloneable": true,
                      "hidden": true,
                      "hasRules": false,
                      "displaySequence": 2,
                      "label": "Product Subtype",
                      "attributeId": "a092E00000W3ARzQAN",
                      "filterable": false,
                      "disabled": true,
                      "readonly": true,
                      "required": false,
                      "multiselect": false,
                      "inputType": "text",
                      "dataType": "text",
                      "code": "SG_ProductSubtype"
                    }
                  ],
                  "totalSize": 3
                },
                "id": "a082E00000XTXr3QAH",
                "Name": "SG Product Rating",
                "Code__c": "SG_ProductRating",
                "displaySequence": 2150
              }
            ]
          },
          "Term": "Annual",
          "childProducts": {
            "totalSize": 0,
            "records": [
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5t0QAB",
                "productName": "Small Group Census",
                "ProductCode": "SG-Census-RF",
                "Name": "Small Group Census",
                "pciId": "a322E000003w55lQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 2,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
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
                            "displaySequence": 0,
                            "label": "Employee Only Count",
                            "attributeId": "a092E00000W3AS3QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "number",
                            "dataType": "number",
                            "code": "SG_empOnlyCount"
                          },
                          {
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
                            "label": "Employee + Spouse Count",
                            "attributeId": "a092E00000W3AS2QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "number",
                            "dataType": "number",
                            "code": "SG_empSpouseCount"
                          },
                          {
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
                            "label": "Employee + Child Count",
                            "attributeId": "a092E00000W3AS5QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "number",
                            "dataType": "number",
                            "code": "SG_empChildCount"
                          },
                          {
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
                            "label": "Employee + Family Count",
                            "attributeId": "a092E00000W3AS4QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "number",
                            "dataType": "number",
                            "code": "SG_empFamilyCount"
                          }
                        ],
                        "totalSize": 4
                      },
                      "id": "a082E00000XTXr4QAH",
                      "Name": "Census",
                      "Code__c": "SG_Census",
                      "displaySequence": 2100
                    },
                    {
                      "productAttributes": {
                        "records": [
                          {
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
                            "displaySequence": 2,
                            "label": "Age",
                            "attributeId": "a092E00000W3ASDQA3",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "number",
                            "dataType": "number",
                            "code": "SG_CM_Age"
                          },
                          {
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
                            "label": "State",
                            "attributeId": "a092E00000W3ASCQA3",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "text",
                            "dataType": "text",
                            "code": "SG_CM_State"
                          },
                          {
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
                            "displaySequence": 6,
                            "label": "Gender",
                            "attributeId": "a092E00000W3ASBQA3",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "text",
                            "dataType": "text",
                            "code": "SG_CM_Gender"
                          },
                          {
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
                            "displaySequence": 7,
                            "label": "Smoker",
                            "attributeId": "a092E00000W3ASKQA3",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "checkbox",
                            "dataType": "text",
                            "code": "SG_CM_Smoker"
                          },
                          {
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
                            "displaySequence": 8,
                            "label": "IsPrimary",
                            "attributeId": "a092E00000W3ASIQA3",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "checkbox",
                            "dataType": "text",
                            "code": "SG_CM_IsPrimary"
                          },
                          {
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
                            "displaySequence": 9,
                            "label": "IsSpouse",
                            "attributeId": "a092E00000W3ASAQA3",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "checkbox",
                            "dataType": "text",
                            "code": "SG_CM_IsSpouse"
                          },
                          {
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
                            "displaySequence": 10,
                            "label": "Birthdate",
                            "attributeId": "a092E00000W3ASMQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "date",
                            "dataType": "date",
                            "code": "SG_CM_Birthdate"
                          },
                          {
                            "userValues": null,
                            "values": [
                              {
                                "disabled": true,
                                "readonly": true
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 11,
                            "label": "MemberClassCode",
                            "attributeId": "a092E00000W3AS7QAN",
                            "filterable": true,
                            "disabled": true,
                            "readonly": true,
                            "required": false,
                            "multiselect": false,
                            "inputType": "text",
                            "dataType": "text",
                            "code": "SG_CM_MemberClassCode"
                          },
                          {
                            "userValues": null,
                            "values": [
                              {
                                "disabled": true,
                                "readonly": true
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 12,
                            "label": "CensusMemberId",
                            "attributeId": "a092E00000W3AS8QAN",
                            "filterable": true,
                            "disabled": true,
                            "readonly": true,
                            "required": false,
                            "multiselect": false,
                            "inputType": "text",
                            "dataType": "text",
                            "code": "SG_CM_CensusMemberId"
                          },
                          {
                            "userValues": null,
                            "values": [
                              {
                                "disabled": true,
                                "readonly": true
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 13,
                            "label": "GroupPlans",
                            "attributeId": "a092E00000W3AS6QAN",
                            "filterable": true,
                            "disabled": true,
                            "readonly": true,
                            "required": false,
                            "multiselect": false,
                            "inputType": "text",
                            "dataType": "text",
                            "code": "SG_CM_GroupPlans"
                          }
                        ],
                        "totalSize": 10
                      },
                      "id": "a082E00000XTXr5QAH",
                      "Name": "CensusMember",
                      "Code__c": "SG_CensusMember",
                      "displaySequence": 2110
                    }
                  ]
                }
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5uTQAR",
                "productName": "Emergency Services",
                "ProductCode": "SG_Emerg_Serv",
                "Name": "Emergency Services",
                "pciId": "a322E000003w55mQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$175 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$175 Copay",
                                "id": "0"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "$150 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$150 Copay",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 1,
                            "label": "Ambulance",
                            "attributeId": "a092E00000W3ATJQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_ambula_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$175 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$175 Copay",
                                "id": "0"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "$150 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$150 Copay",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 2,
                            "label": "Ambulance",
                            "attributeId": "a092E00000W3ATKQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_ambula_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$250 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$250 Copay",
                                "id": "0"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "$175 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$175 Copay",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              },
                              {
                                "value": "$125 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$125 Copay",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 3,
                            "label": "Emergency Room",
                            "attributeId": "a092E00000W3ATLQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_emergRoom_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$500 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$500 Copay",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 4,
                            "label": "Emergency Room",
                            "attributeId": "a092E00000W3ATMQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_emergRoom_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$100 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$100 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$150 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$150 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "$50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$50 Copay",
                                "id": "3"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 5,
                            "label": "Urgent Care Facility",
                            "attributeId": "a092E00000W3ATNQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_urgentCareFacility_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 6,
                            "label": "Urgent Care Facility",
                            "attributeId": "a092E00000W3ATOQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_urgentCareFacility_OON"
                          }
                        ],
                        "totalSize": 6
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_urgentCareFacility_OON\":\"Not Covered\",\"SG_urgentCareFacility_INN\":\"$100 Copay\",\"SG_emergRoom_OON\":\"$500 Copay\",\"SG_emergRoom_INN\":\"$250 Copay\",\"SG_ambula_OON\":\"$175 Copay\",\"SG_ambula_INN\":\"$175 Copay\"}",
                "Id": "a3n2E000005DRMdQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5uUQAR",
                "productName": "Health Savings Account",
                "ProductCode": "SG_HSA",
                "Name": "Health Savings Account",
                "pciId": "a322E000003w55nQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Yes",
                                "disabled": false,
                                "readonly": false,
                                "label": "Yes",
                                "id": "0"
                              },
                              {
                                "value": "No",
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
                            "displaySequence": 7,
                            "label": "Health Savings Account Eligible",
                            "attributeId": "a092E00000W3ATPQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_HSA _INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Yes",
                                "disabled": false,
                                "readonly": false,
                                "label": "Yes",
                                "id": "0"
                              },
                              {
                                "value": "No",
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
                            "displaySequence": 8,
                            "label": "Health Savings Account Eligible",
                            "attributeId": "a092E00000W3ATQQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_HSA _OON"
                          }
                        ],
                        "totalSize": 2
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_HSA _OON\":\"Yes\",\"SG_HSA _INN\":\"Yes\"}",
                "Id": "a3n2E000005DRMeQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5uVQAR",
                "productName": "Hospital Based Services",
                "ProductCode": "SG_Hosp_based_Serv",
                "Name": "Hospital Based Services",
                "pciId": "a322E000003w55oQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 9,
                            "label": "In-Patient Hospital Care",
                            "attributeId": "a092E00000W3ATRQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_inPatientHosp_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 10,
                            "label": "In-Patient Hospital Care",
                            "attributeId": "a092E00000W3ATSQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_inPatientHosp_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 10,
                            "label": "In-Patient Mental Health",
                            "attributeId": "a092E00000W3ATTQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_inpatientMental_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 12,
                            "label": "In-Patient Mental Health",
                            "attributeId": "a092E00000W3ATUQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_inpatientMental_OON"
                          }
                        ],
                        "totalSize": 4
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_inpatientMental_OON\":\"Not Covered\",\"SG_inpatientMental_INN\":\"20% Coins After Ded\",\"SG_inPatientHosp_OON\":\"Not Covered\",\"SG_inPatientHosp_INN\":\"20% Coins After Ded\"}",
                "Id": "a3n2E000005DRMfQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5uWQAR",
                "productName": "Laboratory Outpatient and Professional Services",
                "ProductCode": "SG_Lab_Outpat_Prof",
                "Name": "Laboratory Outpatient and Professional Services",
                "pciId": "a322E000003w55pQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$50 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$35 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$35 Copay",
                                "id": "1"
                              },
                              {
                                "value": "$75 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$75 Copay",
                                "id": "2"
                              },
                              {
                                "value": "$125 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$125 Copay",
                                "id": "3"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "4"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "5"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 13,
                            "label": "Outpatient Lab/X-Ray",
                            "attributeId": "a092E00000W3ATVQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientXray_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 14,
                            "label": "Outpatient Lab/X-Ray",
                            "attributeId": "a092E00000W3ATWQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientXray_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 15,
                            "label": "Outpatient Mental Health",
                            "attributeId": "a092E00000W3ATXQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientMental_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 16,
                            "label": "Outpatient Mental Health",
                            "attributeId": "a092E00000W3ATYQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientMental_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 17,
                            "label": "Outpatient Rehab Services",
                            "attributeId": "a092E00000W3ATZQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientRehab_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 18,
                            "label": "Outpatient Rehab Services",
                            "attributeId": "a092E00000W3ATaQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientRehab_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$75 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$75 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$100 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$100 Copay",
                                "id": "1"
                              },
                              {
                                "value": "$150 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$150 Copay",
                                "id": "2"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "3"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 19,
                            "label": "Outpatient Surgery",
                            "attributeId": "a092E00000W3ATbQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientSurg_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 20,
                            "label": "Outpatient Surgery",
                            "attributeId": "a092E00000W3ATcQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_outpatientSurg_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 21,
                            "label": "Skilled Nursing Facility Care",
                            "attributeId": "a092E00000W3ATdQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_skilledNursing_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 22,
                            "label": "Skilled Nursing Facility Care",
                            "attributeId": "a092E00000W3ATeQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_skilledNursing_OON"
                          }
                        ],
                        "totalSize": 10
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_skilledNursing_OON\":\"Not Covered\",\"SG_skilledNursing_INN\":\"20% Coins After Ded\",\"SG_outpatientSurg_OON\":\"Not Covered\",\"SG_outpatientSurg_INN\":\"$75 Copay\",\"SG_outpatientRehab_OON\":\"Not Covered\",\"SG_outpatientRehab_INN\":\"20% Coins After Ded\",\"SG_outpatientMental_OON\":\"30% Coins After Ded\",\"SG_outpatientMental_INN\":\"20% Coins After Ded\",\"SG_outpatientXray_OON\":\"Not Covered\",\"SG_outpatientXray_INN\":\"$50 Copay\"}",
                "Id": "a3n2E000005DRMgQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5uYQAR",
                "productName": "Medical Plan Information",
                "ProductCode": "SG_Med_Base",
                "Name": "Medical Plan Information",
                "pciId": "a322E000003w55qQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$500 Indiv | $1,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$500 Indiv | $1,000 Fam",
                                "id": "0"
                              },
                              {
                                "value": "$5,000 Indiv | $10,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$5,000 Indiv | $10,000 Fam",
                                "id": "1"
                              },
                              {
                                "value": "$1,000 Indiv| $2,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$1,000 Indiv | $2,000 Fam",
                                "id": "2"
                              },
                              {
                                "value": "$7,500 Indiv | $15,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$7,500 Indiv | $15,000 Fam",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 23,
                            "label": "Annual Deductible",
                            "attributeId": "a092E00000W3ATfQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_annualDed_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "$1,000 Indiv | $2,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$1,000 Indiv | $2,000 Fam",
                                "id": "1"
                              },
                              {
                                "value": "$10,000 Indiv | $20,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$10,000 Indiv | $20,000 Fam",
                                "id": "2"
                              },
                              {
                                "value": "$2,000 Indiv | $4,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$2,000 Indiv | $4,000 Fam",
                                "id": "3"
                              },
                              {
                                "value": "$15,000 Indiv | $30,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$15,000 Indiv | $30,000 Fam",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 24,
                            "label": "Annual Deductible",
                            "attributeId": "a092E00000W3ATgQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_annualDed_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$1,500 Indiv | $3,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$1,500 Indiv | $3,000 Fam",
                                "id": "0"
                              },
                              {
                                "value": "$1,750 Indiv | $3,500 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$1,750 Indiv | $3,500 Fam",
                                "id": "1"
                              },
                              {
                                "value": "$7,500 Indiv | $15,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$7,500 Indiv | $15,000 Fam",
                                "id": "2"
                              },
                              {
                                "value": "$10,000 Indiv | $25,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$10,000 Indiv | $25,000 Fam",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 25,
                            "label": "Annual OOP Limit",
                            "attributeId": "a092E00000W3AThQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_annualOOP_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "$3,500 Indiv | $7,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$3,500 Indiv | $7,000 Fam",
                                "id": "1"
                              },
                              {
                                "value": "$15,000 Indiv | $30,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$15,000 Indiv | $30,000 Fam",
                                "id": "2"
                              },
                              {
                                "value": "$3,000 Indiv | $6,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$3,000 Indiv | $6,000 Fam",
                                "id": "3"
                              },
                              {
                                "value": "$20,000 Indiv | $50,000 Fam",
                                "disabled": false,
                                "readonly": false,
                                "label": "$20,000 Indiv | $50,000 Fam",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 26,
                            "label": "Annual OOP Limit",
                            "attributeId": "a092E00000W3ATiQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_annualOOP_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "20% After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% After Ded",
                                "id": "0"
                              },
                              {
                                "value": "30% After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% After Ded",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 27,
                            "label": "Coinsurance",
                            "attributeId": "a092E00000W3ATjQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_coinsurance_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 28,
                            "label": "Coinsurance",
                            "attributeId": "a092E00000W3ATkQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_coinsurance_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Unlimited",
                                "disabled": false,
                                "readonly": false,
                                "label": "Unlimited",
                                "id": "0"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 29,
                            "label": "Lifetime Maximum",
                            "attributeId": "a092E00000W3ATlQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_lifetimeMax_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Unlimited",
                                "disabled": false,
                                "readonly": false,
                                "label": "Unlimited",
                                "id": "0"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 30,
                            "label": "Lifetime Maximum",
                            "attributeId": "a092E00000W3ATmQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_lifetimeMax_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$0 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$0 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$0",
                                "disabled": false,
                                "readonly": false,
                                "label": "$0",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 31,
                            "label": "Preventive Services",
                            "attributeId": "a092E00000W3ATnQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_preventative_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$0 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$0 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$0",
                                "disabled": false,
                                "readonly": false,
                                "label": "$0",
                                "id": "1"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 32,
                            "label": "Preventive Services",
                            "attributeId": "a092E00000W3AToQAN",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_preventative_OON"
                          }
                        ],
                        "totalSize": 10
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_preventative_OON\":\"$0 Copay\",\"SG_preventative_INN\":\"$0 Copay\",\"SG_lifetimeMax_OON\":\"Unlimited\",\"SG_lifetimeMax_INN\":\"Unlimited\",\"SG_coinsurance_OON\":\"Not Covered\",\"SG_coinsurance_INN\":\"20% After Ded\",\"SG_annualOOP_OON\":\"Not Covered\",\"SG_annualOOP_INN\":\"$1,500 Indiv | $3,000 Fam\",\"SG_annualDed_OON\":\"Not Covered\",\"SG_annualDed_INN\":\"$500 Indiv | $1,000 Fam\"}",
                "Id": "a3n2E000005DRMhQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5uZQAR",
                "productName": "Primary Care Visit",
                "ProductCode": "SG_Pri_Care_Visit",
                "Name": "Primary Care Visit",
                "pciId": "a322E000003w55rQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$25 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$25 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$35 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$35 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 55,
                            "label": "Primary Care Visit",
                            "attributeId": "a092E00000W3AUBQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_primaryCare_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 56,
                            "label": "Primary Care Visit",
                            "attributeId": "a092E00000W3AUCQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_primaryCare_OON"
                          }
                        ],
                        "totalSize": 2
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_primaryCare_OON\":\"Not Covered\",\"SG_primaryCare_INN\":\"$25 Copay\"}",
                "Id": "a3n2E000005DRMiQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5ubQAB",
                "productName": "Specialist Visit",
                "ProductCode": "SG_Specialist",
                "Name": "Specialist Visit",
                "pciId": "a322E000003w55sQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$50 Copay",
                                "id": "0"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "$75 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$75 Copay",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 57,
                            "label": "Specialist",
                            "attributeId": "a092E00000W3AUDQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_specialist_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 58,
                            "label": "Specialist",
                            "attributeId": "a092E00000W3AUEQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_specialist_OON"
                          }
                        ],
                        "totalSize": 2
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_specialist_OON\":\"Not Covered\",\"SG_specialist_INN\":\"$50 Copay\"}",
                "Id": "a3n2E000005DRMjQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5uaQAB",
                "productName": "X-rays and Diagnostic Imaging",
                "ProductCode": "SG_Xray_Diagnostic",
                "Name": "X-rays and Diagnostic Imaging",
                "pciId": "a322E000003w55tQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$125 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$125 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$150 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$150 Copay",
                                "id": "1"
                              },
                              {
                                "value": "$250 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$250 Copay",
                                "id": "2"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "3"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 59,
                            "label": "Imaging",
                            "attributeId": "a092E00000W3AUFQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_imaging_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 60,
                            "label": "Imaging",
                            "attributeId": "a092E00000W3AUGQA3",
                            "filterable": true,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_imaging_OON"
                          }
                        ],
                        "totalSize": 2
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_imaging_OON\":\"Not Covered\",\"SG_imaging_INN\":\"$125 Copay\"}",
                "Id": "a3n2E000005DRMkQAO"
              },
              {
                "displaySequence": -1,
                "productId": "01t2E00000Ne5ucQAB",
                "productName": "Prescription Drugs",
                "ProductCode": "SG_Prescript_drugs",
                "Name": "Prescription Drugs",
                "pciId": "a322E000003w55uQAA",
                "isOptional": false,
                "attributeCategories": {
                  "totalSize": 1,
                  "records": [
                    {
                      "productAttributes": {
                        "records": [
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$37.50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$37.50 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$62.50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$62.50 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 35,
                            "label": "Mail Order Drugs–Tier 1 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATrQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT1_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 36,
                            "label": "Mail Order Drugs–Tier 1 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATsQAN",
                            "filterable": false,
   ..                         "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT1_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$87.50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$87.50 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$125 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$125 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 37,
                            "label": "Mail Order Drugs–Tier 2 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATtQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT2_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 38,
                            "label": "Mail Order Drugs–Tier 2 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATuQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT2_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$125 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$125 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$187.50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$187.50 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 39,
                            "label": "Mail Order Drugs–Tier 3 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATvQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT3_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 40,
                            "label": "Mail Order Drugs–Tier 3 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATwQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT3_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$187.50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$187.50 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$375.00 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$375.00 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 41,
                            "label": "Mail Order Drugs–Tier 4 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATxQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT4_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 42,
                            "label": "Mail Order Drugs–Tier 4 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATyQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT4_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$1,250 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$1,250 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$1,875 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$1,875 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 43,
                            "label": "Mail Order Drugs–Tier 5 (90-Day Supply)",
                            "attributeId": "a092E00000W3ATzQAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT5_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 44,
                            "label": "Mail Order Drugs–Tier 5 (90-Day Supply)",
                            "attributeId": "a092E00000W3AU0QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_mailOrderDrugsT5_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$15 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$15 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$25 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$25 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 45,
                            "label": "Retail Drugs–Tier 1",
                            "attributeId": "a092E00000W3AU1QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT1_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "$55 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$55 Copay",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 46,
                            "label": "Retail Drugs–Tier 1",
                            "attributeId": "a092E00000W3AU2QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT1_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$35 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$35 Copay",
                                "id": "0"
                              },
                              {
                                "value": "$50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$50 Copay",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 47,
                            "label": "Retail Drugs–Tier 2",
                            "attributeId": "a092E00000W3AU3QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT2_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "$75 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$75 Copay",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 48,
                            "label": "Retail Drugs–Tier 2",
                            "attributeId": "a092E00000W3AU4QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT2_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$50 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$50 Copay",
                                "id": "0"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "$75 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$75 Copay",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 49,
                            "label": "Retail Drugs–Tier 3",
                            "attributeId": "a092E00000W3AU5QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT3_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "1"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "$95 Copay",
                                "disabled": false,
                                "readonly": false,
                                "label": "$95 Copay",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 50,
                            "label": "Retail Drugs–Tier 3",
                            "attributeId": "a092E00000W3AU6QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT3_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "$75 Copay After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "$75 Copay After Ded",
                                "id": "0"
                              },
                              {
                                "value": "$150 Copay After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "$150 Copay After Ded",
                                "id": "1"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 51,
                            "label": "Retail Drugs–Tier 4",
                            "attributeId": "a092E00000W3AU7QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT4_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "$175 Copay After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "$175 Copay After Ded",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 52,
                            "label": "Retail Drugs–Tier 4",
                            "attributeId": "a092E00000W3AU8QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT4_OON"
                          },
                          {
                            "attributeGroupType": "In-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "$500 Copay After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "$500 Copay After Ded",
                                "id": "1"
                              },
                              {
                                "value": "$750 Copay After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "$750 Copay After Ded",
                                "id": "2"
                              },
                              {
                                "value": "20% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "20% Coins After Ded",
                                "id": "3"
                              },
                              {
                                "value": "30% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "30% Coins After Ded",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 53,
                            "label": "Retail Drugs–Tier 5",
                            "attributeId": "a092E00000W3AU9QAN",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT5_INN"
                          },
                          {
                            "attributeGroupType": "Out-Of-Network",
                            "userValues": null,
                            "values": [
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "0"
                              },
                              {
                                "value": "Not Covered",
                                "disabled": false,
                                "readonly": false,
                                "label": "Not Covered",
                                "id": "1"
                              },
                              {
                                "value": "40% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "40% Coins After Ded",
                                "id": "2"
                              },
                              {
                                "value": "50% Coins After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "50% Coins After Ded",
                                "id": "3"
                              },
                              {
                                "value": "$525 Copay After Ded",
                                "disabled": false,
                                "readonly": false,
                                "label": "$525 Copay After Ded",
                                "id": "4"
                              }
                            ],
                            "isNotTranslatable": false,
                            "cloneable": true,
                            "hidden": false,
                            "hasRules": false,
                            "displaySequence": 54,
                            "label": "Retail Drugs–Tier 5",
                            "attributeId": "a092E00000W3AUAQA3",
                            "filterable": false,
                            "disabled": false,
                            "readonly": false,
                            "required": false,
                            "multiselect": false,
                            "inputType": "dropdown",
                            "dataType": "text",
                            "code": "SG_RetailDrugsT5_OON"
                          }
                        ],
                        "totalSize": 20
                      },
                      "id": "a082E00000XTXs4QAH",
                      "Name": "SG Medical",
                      "Code__c": "SG_Medical",
                      "displaySequence": 2000
                    }
                  ]
                },
                "attributeSelectedValues": "{\"SG_RetailDrugsT5_OON\":\"Not Covered\",\"SG_RetailDrugsT5_INN\":\"Not Covered\",\"SG_RetailDrugsT4_OON\":\"Not Covered\",\"SG_RetailDrugsT4_INN\":\"$75 Copay After Ded\",\"SG_RetailDrugsT3_OON\":\"Not Covered\",\"SG_RetailDrugsT3_INN\":\"$50 Copay\",\"SG_RetailDrugsT2_OON\":\"Not Covered\",\"SG_RetailDrugsT2_INN\":\"$35 Copay\",\"SG_RetailDrugsT1_OON\":\"Not Covered\",\"SG_RetailDrugsT1_INN\":\"$15 Copay\",\"SG_mailOrderDrugsT5_OON\":\"Not Covered\",\"SG_mailOrderDrugsT5_INN\":\"$1,250 Copay\",\"SG_mailOrderDrugsT4_OON\":\"Not Covered\",\"SG_mailOrderDrugsT4_INN\":\"$187.50 Copay\",\"SG_mailOrderDrugsT3_OON\":\"Not Covered\",\"SG_mailOrderDrugsT3_INN\":\"$125 Copay\",\"SG_mailOrderDrugsT2_OON\":\"Not Covered\",\"SG_mailOrderDrugsT2_INN\":\"$87.50 Copay\",\"SG_mailOrderDrugsT1_OON\":\"Not Covered\",\"SG_mailOrderDrugsT1_INN\":\"$37.50 Copay\"}",
                "Id": "a3n2E000005DRMlQAO"
              }
            ]
          },
          "dependents": {
            "totalSize": 0,
            "records": [
              {
                "displaySequence": -1,
                "Id": "a3p2E000002dovOQAQ",
                "First Name": "Laura",
                "Last Name": "Border",
                "contactId": "0032E00002Znpm4QAB",
                "partyId": "a0x2E00000BO8d4QAD"
              }
            ]
          }
        }
      ]
    }
  }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service creates no output JSON.

.

Did this article solve your issue?

Let us know so we can improve!

YesNo