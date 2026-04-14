---
title: "External Rating and Pricing"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_external_rating_and_pricing_610958.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# External Rating and Pricing

External Rating and Pricing[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# External Rating and Pricing

For external rating and `createUpdateQuote`, you must use the simplified quote JSON optimized for ease of mapping with external policy admin systems. You can generate a simplified quote JSON response using the `[InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")` service.

For example, when a quote is repriced using the rate now button, the rating Integration Procedure invokes `[InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")` and generates the simplified JSON that is sent to the external system through an HTTP action or an apex class. The response returned from the external system is in the same simplified json format, which is consumed by the rating services to update the quote record with the information returned.

Set up the product to use an external system:

1.  [](https://help.salesforce.com/s?language=en_US)
    
    Set up the Product.
    
    1.  `External ID` must have a value.
        
    2.  Set `Rating Procedure Type` = Integration Procedure.
        
    3.  Set `Rating Procedure Name` = Integration Procedure’s Type\_Subtype.
        
2.  Set up the Integration Procedure to call an external system for Rating or Pricing.
    
    Important
    
    Set the org to allow requests to the external system’s endpoint. You can do this setting in Set Up > Security > Remote Site Settings.
    
    1.  Invoke `[InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")` with option `isForExternal=true`, and input `action=reprice` to prepare the Quote JSON.
        
    2.  Send the [Quote JSON](https://help.salesforce.com/s/articleView?id=ind.insurance_external_rating_and_pricing_610958.htm&language=en_US&type=5 "For external rating and createUpdateQuote, you must use the simplified quote JSON optimized for ease of mapping with external policy admin systems. You can generate a simplified quote JSON response using the *** service.") to the external system for the rating. Create an Apex class that sends the request to the external system or use the HTTP action in the Integration Procedure.
        
    3.  Expect the external system to [return a Quote JSON](https://help.salesforce.com/s/articleView?id=ind.insurance_external_rating_and_pricing_610958.htm&language=en_US&type=5 "For external rating and createUpdateQuote, you must use the simplified quote JSON optimized for ease of mapping with external policy admin systems. You can generate a simplified quote JSON response using the *** service.") with the prices updates.
        
    4.  The format for the `ResponseAction`:
        
        ```json
        {
          "result": {
            "quote": {
              // This is the updated Quote JSON returned in #2
            },
            "errorCode": "INVOKE-200",
            "error": "OK"
          }
        }
        ```
        
        Important
        
        When using the HTTP action, the result omits `“error”: “OK”`. Add this error manually using the additional output option of the `ResponseAction`.
        
        The error code `INVOKE-200` indicates that the request was received. Other messages include information about the records created by the service.
        
        If the service doesn't generate the output you expect, check the debug log for information about potential configuration issues.
        

[](https://help.salesforce.com/s?language=en_US)

## Input JSON for InsQuoteService: createUpdateQuoteFromExternal

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

## Output JSON for InsQuoteService: createUpdateQuoteFromExternal

The service returns the `Quote.Id` of the created or updated quote in the output JSON and the list of errors encountered.

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