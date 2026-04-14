---
title: "InsQuoteService:createUpdateQuoteFromExternal"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequotefromexternal.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:createUpdateQuoteFromExternal

InsQuoteService:createUpdateQuoteFromExternal[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:createUpdateQuoteFromExternal

Creates a quote or updates an existing quote with new information through an inbound API call from an external system.

Class:`InsQuoteService`

Method: `createUpdateQuoteFromExternal`

[](https://help.salesforce.com/s?language=en_US)

## How it Works

1.  Receives the JSON object.
    
2.  Uses the `sourceSystemIdentifier` to determine whether to create or update an existing quote.
    
3.  Uses the `PricebookId`, which is a Price book named Standard.
    
4.  If the service finds a Quote with the given `sourceSystemIdentifier`, it updates the quote object:
    
    1.  Uses the root products defined in `quoteLines` to add, update, or delete the root quote line items. The service uses the `sourceSystemIdentifier` for identifying the root.
        
        Adds the records in `quoteLines` that aren’t in the Quote. Updates the records in `quoteLines` existing in the Quote. Deletes the records in `quoteLines` that are in the Quote but not in the quoteLines.
        
    2.  For each root, the service uses the coverages, insured items, and parties defined in `childLines` to add, update, or delete the root coverages, insured items, and parties. The service uses the `sourceSystemIdentifier` for identifying the line to update.
        
        Adds the records in `childLines` that aren’t in the Quote. Updates the records in `childLines` existing in the Quote. Deletes the records in `childLines` that are in the Quote but not in `childLines`.
        
    3.  For each root coverage, insured items, and parties, the service uses the coverages, insured items, and parties in the `childLines` to add, update, or delete the respective coverages, insured items, and parties. The service uses `sourceSystemIdentifier` for identifying the line to update.
        
        Adds the records in `childLines` that aren’t in the Quote. Updates the records in `childLines` existing in the Quote. Deletes the records in `childLines` that are in the Quote but not in `childLines`.
        
    4.  The primary insured item's `QuoteLineItem` and child insured party `QuoteLineItem` records have a many:many relationship. These relationships are stored in the Quote Item Relationship (`QuoteItemRelationship__c`) object. If an insured item `QuoteLineItem` has relationships to multiple insured party `QuoteLineItem` records, the service uses the `PrimaryChildLineItemId__c` field to determine which of those relationships is the primary one.
        
        For example, both Joan Smith and John Smith are drivers of Lexus 250; Joan Smith is set as the primary driver. The Lexus 250 `QuoteLineItem` has `PrimaryChildLineItemId__c` pointing to Joan Smith's `QuoteLineItem`.
        
    5.  If two insured items have the same child insured party, each insured item must have an entry in the respective `childLines` for the child insured party. For both entries, they must have the same `sourceSystemIdentifier`.
        
        For example, both Lexus 250 and Honda Odyssey have Bob Jones as a driver. Lexus 250 has Bob Jones with `sourceSystemIdentifier` as BobJones in its `childLines`. Honda Odyssey has a Bob Jones with `sourceSystemIdentifier` as BobJones in its `childLines`.
        
    6.  ParentItemId\_\_c and ParentItemId2\_\_c of `childLines` point to the root's Id.
        
    7.  Child coverages' `SubParentItemId__c` points to the primary insured item.
        
5.  If the service doesn't find a quote with the given `sourceSystemIdentifier`, it creates the quote object that includes line items as explained here:
    
    1.  Uses the root products defined in `quoteLines` to create the root quote line items.
        
    2.  For each root, uses the coverages, insured items, and parties defined in `childLines` to create the root coverages, insured items, and parties.
        
    3.  For each root coverage, insured items and parties, uses the coverages, insured items, and parties defined in their `childLines` to create their coverages, insured items, and parties.
        
    4.  The primary insured item's `QuoteLineItem` and child insured party `QuoteLineItem` records have a many:many relationship. These relationships are stored in the Quote Item Relationship (`QuoteItemRelationship__c`) object. If an insured item `QuoteLineItem` has relationships to multiple insured party `QuoteLineItem` records, the service uses `PrimaryChildLineItemId__c` field to determine which of those relationships is the primary one.
        
        For example, both Joan Smith and John Smith are drivers of Lexus 250; Joan Smith is set as the primary driver. The Lexus 250 `QuoteLineItem` has `PrimaryChildLineItemId__c` pointing to Joan Smith's `QuoteLineItem`.
        
    5.  If two insured items have the same child insured party, each insured item must have entry in the respective `childLines` for the child insured party. For both entries, they must have the same `sourceSystemIdentifier`.
        
        For example, both Lexus 250 and Honda Odyssey have Bob Jones as a driver. Lexus 250 has Bob Jones with `sourceSystemIdentifier` as BobJones in its `childLine`s. Honda Odyssey has Bob Jones with `sourceSystemIdentifier` as BobJones in its `childLines`.
        
    6.  `ParentItemId__c` and `ParentItemId2__c` of `childLines` point to the root's Id.
        
    7.  Child coverages' `SubParentItemId__c` point to the primary insured item.
        
6.  Returns a `Quote.Id` and the list of errors encountered in the output JSON.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`quote`

 | 

Contains all the information for the creation of the quote. For more information on the key-value pairs, see JSON Nodes description.

 |
| 

JSON Nodes description

 |
| 

`quote`

 | 

A list of records. The service processes only one quote at a given time.

 |
| 

quote nodes

 |
| 

`opportunityId`

 | 

Required.

The Id of the opportunity.

 |
| 

`sourceSystemIdentifier`

 | 

Required.

Unique record identifier from a system outside of Salesforce to identify which quote to update.

 |
| 

`type`

 | 

The API name of quote record type.

 |
| 

`additionalFields`

 | 

The key-value pair of other `QuoteLineItem` fields that you want to populate.

 |
| 

`quoteLines`

 | 

The list of root products.

 |
| 

quoteLines nodes

 |
| 

`sourceSystemIdentifier`

 | 

Required.

Unique record identifier from a system outside of Salesforce to identify which root QuoteLineItems to add, update, or delete in Salesforce.

 |
| 

`instanceKey`

 | 

Instance key in `ItemName__c` of root products.

 |
| 

`productCode`

 | 

Required.

Root product code.

 |
| 

`lineRecordType`

 | 

Required.

Product or specification record type.

 |
| 

`attributeCategories`

 | 

The selected product attributes.

 |
| 

`additionalFields`

 | 

The key-value pair of other `QuoteLineItem` fields that you want to populate.

 |
| 

`childLines`

 | 

Root product coverages, insured items, and insured parties.

 |
| 

childLines nodes

 |
| 

`sourceSystemIdentifier`

 | 

Required.

Unique record identifier from a system outside of Salesforce to identify which root coverages, insured items, and insured parties to add, update, or delete in Salesforce.

 |
| 

`instanceKey`

 | 

Identifies multiple instances of the same spec.

Instance key in `ItemName__c` of insured items, and insured parties.

 |
| 

`productCode`

 | 

Required.

The product code of root coverages, insured items, and insured parties.

 |
| 

`lineRecordType`

 | 

Required.

Product or specification record type.

 |
| 

`attributeCategories`

 | 

The selected product attributes.

 |
| 

`additionalFields`

 | 

The key-value pair of other `QuoteLineItem` fields that you want to populate.

 |
| 

`childLines`

 | 

Child coverages, insured items, and insured parties.

 |
| 

childLines nodes

 |
| 

`sourceSystemIdentifier`

 | 

Required.

Unique record identifier from a system outside of Salesforce to identify which child coverages, insured items, and insured parties to add, update, or delete in Salesforce.

If two insured items have the same child insured party, each insured item must have entry in the respective `childLines` for the child insured party. For both entries, they must have the same `sourceSystemIdentifier`. See [InsQuoteService:createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.").

 |
| 

`instanceKey`

 | 

Identifies multiple instances of the same spec.

Instance key in `ItemName__c` of insured items, and insured parties.

 |
| 

`productCode`

 | 

Required.

The product code of child coverages, insured items, and insured parties product.

 |
| 

`lineRecordType`

 | 

Required.

Product or specification record type.

 |
| 

`attributeCategories`

 | 

The selected product attributes.

 |
| 

`additionalFields`

 | 

The key-value pair of other `QuoteLineItem` fields that you want to populate.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```json
{
   "quote":{
      "records":[
         {
            "opportunityId":"Opportunity.Id",
            "sourceSystemIdentifier":"Id",
            "sourceSystem":"Name of system quote was created",
            "Name":"Quote Name",
            "type":"Quote.RecordType.DeveloperName",
            "effectiveDate":"Quote.EffectiveDate__c",
            "endDate":"Quote.EndDate__c",
            "price":Quote.StandardPremium__c,
            "term":"Quote.Term__c",
            "status":"Quote.Status",
            "additionalFields":{
               "Quote.fieldAPIName":"value"
            },
            "quoteLines":{
               "records":[
                  {
                     "sourceSystemIdentifier":"Id",
					 "lineRecordType":"Product2",
                     "instanceKey":"name",
                     "productCode":"Product2.ProductCode",
                     "productName":"Product2.Name",
                     "attributeCategories":{
                        "records":[
                           {
                              "productAttributes":{
                                 "records":[
                                    {
                                       "code":"attribute code",
                                       "userValues":"selected value"
                                    }
                                 ]
                              }
                           }
                        ]
                     },
                     "additionalFields":{
                        "QuoteLineItem.fieldAPIName":"value"
                     },
                     "childLines":{
                        "records":[
                           {
                              "sourceSystemIdentifier":"Id",
                              "lineRecordType":"Product2.RecordType.DeveloperName",
                              "productCode":"Product2.ProductCode",
                              "productName":"Product2.Name",
                              "instanceKey":"instance name",
                              "price":QuoteLineItem.UnitPrice,
                              "taxAmount":QuoteLineItem.TaxAmount__c,
                              "feeAmount":QuoteLineItem.FeeAmount__c,
                              "additionalFields":{
                                 "QuoteLineItem.fieldAPIName":"value"
                              },
                              "attributeCategories":{
                                 "records":[
                                    {
                                       "productAttributes":{
                                          "records":[
                                             {
                                                "code":"attribute code",
                                                "userValues":"selected value"
                                             }
                                          ]
                                       }
                                    }
                                 ]
                              },
                              "childLines":{
                                 "records":[
                                    {
                                       "sourceSystemIdentifier":"Id",7e54f959544f",
                                       "lineRecordType":"InsuredPartySpec",
                                       "productCode":"Product2.ProductCode",
                                       "productName":"Product2.Name",
                                       "instanceKey":"instance name",
                                       "price":QuoteLineItem.UnitPrice,
                                       "taxAmount":QuoteLineItem.TaxAmount__c,
                                       "feeAmount":QuoteLineItem.FeeAmount__c,
                                       "isPrimaryChild":true,
                                       "additionalFields":{
                                          "QuoteLineItem.fieldAPIName":"value"
                                       },
                                       "attributeCategories":{
                                          "records":[
                                             {
                                                "productAttributes":{
                                                   "records":[
                                                      {
                                                         "code":"attribute code",
                                                         "userValues":"selected value"
                                                      }
                                                   ]
                                                }
                                             }
                                          ]
                                       }
                                    }
                                 ]
                              }
                           }
                        ]
                     }
                  }
               ]
            }
         }
      ]
   }
}
```

Here's an example of the input JSON:

```json
{
  "quote": {
    "records": [
      {
        "opportunityId": "0065w0000286hhNAAQ",
        "sourceSystemIdentifier": "af3c0072-9018-43df-83d3-3a5f254d5b1e",
        "sourceSystem": "Salesforce",
        "Name": "Auto Root (External)",
        "type": "LargeGroupQuote",
        "effectiveDate": "06/01/2021",
        "endDate": "12/01/2021",
        "price": 10000,
        "term": "Semi-Annual",
        "status": "Submitted",
        "quoteLines": {
          "records": [
            {
              "sourceSystemIdentifier": "49553393-120a-4777-b65a-8167c386a0fb",
              "instanceKey": "Auto Root",
              "productCode": "AUTOROOT",
              "productName": "Auto Root",
              "attributeCategories": {
                "records": [
                  {
                    "productAttributes": {
                      "records": [
                        {
                          "code": "atLimitUM",
                          "userValues": 200
                        }
                      ]
                    }
                  }
                ]
              },
              "additionalFields": {
                "instest12__AdjustmentComments__c": "test comment"
              },
              "childLines": {
                "records": [
                  {
                    "sourceSystemIdentifier": "5a8d1b04-c34c-6a48-42c8-ab08be9868e1",
                    "lineRecordType": "InsuredItemSpec",
                    "Name": "Auto",
                    "productName": "Auto",
                    "productCode": "AUTO",
                    "instanceKey": "2010 Honda Odyssey",
                    "price": 111,
                    "taxAmount": 5,
                    "feeAmount": 21,
                    "additionalFields": {
                      "instest12__AdjustmentComments__c": "test comment"
                    },
                    "attributeCategories": {
                      "records": [
                        {
                          "productAttributes": {
                            "records": [
                              {
                                "code": "autoYear",
                                "userValues": 2010
                              },
                              {
                                "code": "carValue",
                                "userValues": 55000
                              },
                              {
                                "code": "est_annual_mileage",
                                "userValues": 2000
                              },
                              {
                                "code": "autoMake",
                                "userValues": "Honda"
                              },
                              {
                                "code": "autoModel",
                                "userValues": "Odyssey"
                              }
                            ]
                          }
                        }
                      ]
                    },
                    "childLines": {
                      "records": [
                        {
                          "sourceSystemIdentifier": "6400140b-3e97-32c4-bdfd-7e54f959544f",
                          "lineRecordType": "InsuredPartySpec",
                          "Name": "Driver",
                          "productName": "Driver",
                          "productCode": "DRIVER",
                          "instanceKey": "Bob Jones",
                          "price": 112,
                          "taxAmount": 6,
                          "feeAmount": 22,
                          "isPrimaryChild": true,
                          "additionalFields": {
                            "instest12__AdjustmentComments__c": "test comment"
                          },
                          "attributeCategories": {
                            "records": [
                              {
                                "productAttributes": {
                                  "records": [
                                    {
                                      "code": "AGE",
                                      "userValues": 24
                                    },
                                    {
                                      "code": "FN",
                                      "userValues": "Bob"
                                    },
                                    {
                                      "code": "LN",
                                      "userValues": "Jones"
                                    },
                                    {
                                      "code": "GENDER",
                                      "userValues": "Male"
                                    }
                                  ]
                                }
                              }
                            ]
                          }
                        },
                        {
                          "sourceSystemIdentifier": "38c4fe27-7b85-77ce-c9e2-1f7f22889982",
                          "lineRecordType": "InsuredPartySpec",
                          "Name": "Driver",
                          "productName": "Driver",
                          "productCode": "DRIVER",
                          "instanceKey": "Joan Smith",
                          "price": 113,
                          "taxAmount": 7,
                          "feeAmount": 23,
                          "attributeCategories": {
                            "records": [
                              {
                                "productAttributes": {
                                  "records": [
                                    {
                                      "code": "AGE",
                                      "userValues": 25
                                    },
                                    {
                                      "code": "FN",
                                      "userValues": "Joan"
                                    },
                                    {
                                      "code": "LN",
                                      "userValues": "Smith"
                                    },
                                    {
                                      "code": "GENDER",
                                      "userValues": "Female"
                                    }
                                  ]
                                }
                              }
                            ]
                          }
                        },
                        {
                          "sourceSystemIdentifier": "33b74fa2-fba5-44b4-317f-021dae689a9f",
                          "lineRecordType": "CoverageSpec",
                          "Name": "Collision Deductible Waiver",
                          "productName": "Collision Deductible Waiver",
                          "productCode": "COL_WAIVER",
                          "instanceKey": "2010 Honda Odyssey_COL_WAIVER",
                          "price": 114,
                          "taxAmount": 8,
                          "feeAmount": 24
                        },
                        {
                          "sourceSystemIdentifier": "c4d5ac35-99b1-047d-cebe-05b74861463e",
                          "lineRecordType": "CoverageSpec",
                          "Name": "Uninsured/Underinsured Motorist BI",
                          "productName": "Uninsured/Underinsured Motorist BI",
                          "productCode": "UNINSURED_COVERAGE",
                          "instanceKey": "2010 Honda Odyssey_UNINSURED_COVERAGE",
                          "price": 115,
                          "taxAmount": 9,
                          "feeAmount": 25,
                          "attributeCategories": {
                            "records": [
                              {
                                "productAttributes": {
                                  "records": [
                                    {
                                      "code": "AbaThrpyOutptInst_covered_inn",
                                      "userValues": 1.3
                                    },
                                    {
                                      "code": "UNINSURED",
                                      "userValues": "No coverage"
                                    }
                                  ]
                                }
                              }
                            ]
                          }
                        }
                      ]
                    }
                  },
                  {
                    "sourceSystemIdentifier": "60699eaf-956a-4381-8ef2-5a704c85517f",
                    "lineRecordType": "InsuredItemSpec",
                    "Name": "Auto",
                    "productName": "Auto",
                    "productCode": "AUTO",
                    "instanceKey": "2011 Toyota Camry",
                    "price": 116,
                    "taxAmount": 10,
                    "feeAmount": 26,
                    "attributeCategories": {
                      "records": [
                        {
                          "productAttributes": {
                            "records": [
                              {
                                "code": "autoYear",
                                "userValues": 2011
                              },
                              {
                                "code": "carValue",
                                "userValues": 55500
                              },
                              {
                                "code": "est_annual_mileage",
                                "userValues": 2200
                              },
                              {
                                "code": "autoMake",
                                "userValues": "Toyota"
                              },
                              {
                                "code": "autoModel",
                                "userValues": "Camry"
                              }
                            ]
                          }
                        }
                      ]
                    },
                    "childLines": {
                      "records": [
                        {
                          "sourceSystemIdentifier": "6400140b-3e97-32c4-bdfd-7e54f959544f",
                          "lineRecordType": "InsuredPartySpec",
                          "Name": "Driver",
                          "productName": "Driver",
                          "productCode": "DRIVER",
                          "instanceKey": "Bob Jones",
                          "price": 112,
                          "taxAmount": 6,
                          "feeAmount": 22,
                          "isPrimaryChild": true,
                          "attributeCategories": {
                            "records": [
                              {
                                "productAttributes": {
                                  "records": [
                                    {
                                      "code": "AGE",
                                      "userValues": 24
                                    },
                                    {
                                      "code": "FN",
                                      "userValues": "Bob"
                                    },
                                    {
                                      "code": "LN",
                                      "userValues": "Jones"
                                    },
                                    {
                                      "code": "GENDER",
                                      "userValues": "Male"
                                    }
                                  ]
                                }
                              }
                            ]
                          }
                        },
                        {
                          "sourceSystemIdentifier": "8c450354-2053-444c-9c9e-36a66e6f5582",
                          "lineRecordType": "CoverageSpec",
                          "Name": "Collision Deductible Waiver",
                          "productName": "Collision Deductible Waiver",
                          "productCode": "COL_WAIVER",
                          "instanceKey": "2011 Toyota Camry_COL_WAIVER",
                          "price": 117,
                          "taxAmount": 11,
                          "feeAmount": 27
                        },
                        {
                          "sourceSystemIdentifier": "7aaeee37-05ce-4926-accb-dff2ee85587f",
                          "lineRecordType": "CoverageSpec",
                          "Name": "Roadside",
                          "productName": "Roadside",
                          "productCode": "ROADSIDE_COVERAGE",
                          "instanceKey": "2011 Toyota Camry_ROADSIDE_COVERAGE",
                          "price": 118,
                          "taxAmount": 12,
                          "feeAmount": 28,
                          "attributeCategories": {
                            "records": [
                              {
                                "productAttributes": {
                                  "records": [
                                    {
                                      "code": "ROADSIDE",
                                      "userValues": 1
                                    }
                                  ]
                                }
                              }
                            ]
                          }
                        }
                      ]
                    }
                  }
                ]
              }
            }
          ]
        },
        "additionalFields": {
          "instest12__MonthlyPremium__c": 222
        }
      }
    ]
  }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Returns the `Quote.Id` of the created or updated quote in the output JSON and the list of errors encountered.

Here's the format of the output JSON:

```json
{
   "errors":[
      "error1",
      "error2",
      "error3"
   ],
   "quoteId":"Quote.Id"
}
```

[](https://help.salesforce.com/s?language=en_US)Here's an example of the output JSON:

```json
{
   "errors":[
      "Failed to create/update QuoteLineItem Honda Odyssey.Required fields are missing: [PricebookEntryId, Product2Id]; ",
      "Failed to create/update QuoteLineItem Toyota Camry.Required fields are missing: [PricebookEntryId, Product2Id]; ",
      "Failed to create/update QuoteLineItem Patty Desc.Required fields are missing: [PricebookEntryId, Product2Id]; "
   ],
   "quoteId":"0Q05w0000027aH5CAI"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo