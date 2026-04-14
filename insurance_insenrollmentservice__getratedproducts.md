---
title: "InsEnrollmentService:getRatedProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservice__getratedproducts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService:getRatedProducts

InsEnrollmentService:getRatedProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService:getRatedProducts

Use the service to return a list of eligible products for a given enrollee and their dependents. The rate band prices for each product are displayed when the plan's rate type is `Composite`.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsEnrollmentService`

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Method: `getRatedProducts`

Important

Looking for the service that returns an array of rated products not related to enrollment? You're in the wrong place.

You want [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.").

[](https://help.salesforce.com/s?language=en_US)

## How It works

1.  This service takes the `userId` or `contactID` and the `contractId` of the enrollee who's logged in to the system, and today's date.
    
2.  The service gets the enrollee and dependents (if applicable) information. It also finds a contract that's valid for today's date--that is, today is within the enrollment start date and enrollment end date.
    
3.  Based on the enrollee's information and the contract, the service gets a list of all products the enrollee and dependents can enroll in.
    
4.  The service uses the filter option to further filter the list of available products.
    
5.  The service calculates the rate of each product. The rating process is based on plan level rating type setting or the integration procedure set at the product level.
    
    -   If the rating type is set to `Composite`, the rate band. information is used to parse the data from `PricingLogData__c` at the contract line level.
        
    -   If the rating type is set to `Age`, the price is calculated from the calculation procedure linked to the product. This service supports all the remote options that are supported in `InsProductService.getRatedProducts`. To know more, read [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.").
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
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

`Product2FieldName:Value,Product2FieldName:%Element Name%`

Use the API name with a colon followed by either a value or a variable. For example, in an OmniScript, a variable can be a name of an element, such as an input picklist.

Separate multiple filter parameters with commas.

Filters can include any field on the `Product2` object.

 |
| 

`includeFilterAttrValues`

 | 

`true` or `false`

Defaults to `false`.

In the output JSON, along with the array of products, this adds the `filterAttrValues` object. This object contains the root product attributes marked filterable, with the possible list of values. This list is used by some UI templates to filter large sets of products. Child product attributes are not included.

 |
| 

`includeInputKeys`

 | 

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

`mergeList`

 | 

`true` or `false`

Defaults to `false`.

Optimizes rating calls by grouping rating procedure calls by products using the same rating procedure. It makes one rating call with an array of input objects.

This is useful when pulling a large list of products. Multiple rating calls can hit SQL limits. The rating procedure architecture is optimized to handle an array of input objects and minimize the number of SQL queries needed.

Calculation Procedures with Aggregation Steps are not supported.

 |
| 

`productClasses`

 | 

“ProductClassName1,ProductClassName2”

Comma separated list of product class names. Limits the list of products to these product classes.

 |
| 

`stage`

 | 

Used as a switch in rating IP.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The service takes the following input JSON if the `censusId` is used as the input (sample Ids are shown):

```
{"userId": "xxxx",
"contactId": "xxxx",
"contractId": "xxx"}
```

The service retrieves `userInputs` from the census member object, specifically from the `member.AttributeSelectedValue__c` field. These attributes need to match the product's expected inputs.

Alternatively, you can define your own userInputs in the following way:

```
"additionalInputs": 
{
    "stage": "Quote"
},
{"userId": "xxxx",
"contactId": "xxxx",
"contractId": "xxx",
"userInputs": 
    [
        {"vBirthdate": "1969-09-20",
        "FamilyTier": "Employee Only"}
    ]
}            
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an array of rated products using the [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates."). This includes any child coverage specs included under childProducts (if any). It also includes price data for all the rate bands for each product.

In this example, the enrollee's contracted options return three products and their rate band tier prices (see the `RateBandTierPriceData` node). Here the rating type is set to `Composite`.

```
{  
   "totalSize":3,
   "records":[  
      {  
         "displaySequence":-1,
         "CalculatedPriceData":{  
            "Family":900.5,
            "Self + Child":555.5,
            "Self + Spouse":590,
            "Self":245
         },
         "Id":"01tf4000002ApR0AAK",
         "Name":"Bronze PPO 5000 (HSA)",
         "Family":"Commercial",
         "ProductCode":"SG-PPO-5000-HSA",
         "LineOfBusiness__c":"Group Health",
         "MarketSegment__c":"Small Group",
         "Type__c":"Medical",
         "SubType__c":"HDHP",
         "IsRecommended__c":false,
         "Tier__c":"Bronze",
         "ImageId__c":"01tf4000002ApR0AAK",
         "PricingSource__c":"GrandTotal",
         "RecordTypeName__c":"Product",
         "IsConfigurable__c":false,
         "productId":"01tf4000002ApR0AAK",
         "Price":"",
         "ImageId":"/sfc/servlet.shepherd/version/renditionDownload?rendition=ORIGINAL_Png&versionId=068f4000002yjYiAAI",
         "planId":"a0sf4000001u0CmAAI",
         "planRateType":"Composite",
         "RateBandTierPriceData":{  
            "Self":{  
               "Price":245,
               "Sequence":"1",
               "Label":"Employee"
            },
            "Self + Spouse":{  
               "Price":590,
               "Sequence":"2",
               "Label":"Employee + Spouse"
            },
            "Self + Child":{  
               "Price":555.5,
               "Sequence":"3",
               "Label":"Employee + Child"
            },
            "Family":{  
               "Price":900.5,
               "Sequence":"5",
               "Label":"Family"
            }
         },
         "childProducts":{  
            ...
         },
         "attributeCategories":{  
            ...
         }         {  
            "displaySequence":-1,
            "CalculatedPriceData":{  
               "Family":1100.5,
               "Self + Child":755.5,
               "Self + Spouse":790,
               "Self":445
            },
            "Id":"01tf4000002ApR8AAK",
            "Name":"Gold PPO 35",
            "Family":"Commercial",
            "ProductCode":"SG-PPO-35",
            "LineOfBusiness__c":"Group Health",
            "MarketSegment__c":"Small Group",
            "Type__c":"Medical",
            "SubType__c":"PPO",
            "IsRecommended__c":false,
            "Tier__c":"Gold",
            "ImageId__c":"01tf4000002ApR8AAK",
            "PricingSource__c":"GrandTotal",
            "RecordTypeName__c":"Product",
            "IsConfigurable__c":true,
            "PricingFormula__c":"Premium",
            "productId":"01tf4000002ApR8AAK",
            "ImageId":"/sfc/servlet.shepherd/version/renditionDownload?rendition=ORIGINAL_Png&versionId=068f4000002yjYjAAI",
            "planId":"a0sf4000001u0ClAAI",
            "planRateType":"Composite",
            "RateBandTierPriceData":{  
               "Self":{  
                  "Price":445,
                  "Sequence":"1",
                  "Label":"Employee"
               },
               "Self + Spouse":{  
                  "Price":790,
                  "Sequence":"2",
                  "Label":"Employee + Spouse"
               },
               "Self + Child":{  
                  "Price":755.5,
                  "Sequence":"3",
                  "Label":"Employee + Child"
               },
               "Family":{  
                  "Price":1100.5,
                  "Sequence":"5",
                  "Label":"Family"
               }
            },
            "childProducts":{  
               ...
            },
            "attributeCategories":{  
               ...
            }
         },
         {  
            "displaySequence":-1,
            "CalculatedPriceData":{  
               "Family":1000.5,
               "Self + Child":655.5,
               "Self + Spouse":690,
               "Self":345
            },
            "Id":"01tf4000002ApQXAA0",
            "Name":"Silver HMO 500",
            "Family":"Commercial",
            "ProductCode":"SG-HMO-500",
            "LineOfBusiness__c":"Group Health",
            "MarketSegment__c":"Small Group",
            "Type__c":"Medical",
            "SubType__c":"HMO",
            "IsRecommended__c":false,
            "Tier__c":"Silver",
            "ImageId__c":"01tf4000002ApQXAA0",
            "PricingSource__c":"GrandTotal",
            "RecordTypeName__c":"Product",
            "IsConfigurable__c":false,
            "productId":"01tf4000002ApQXAA0",
            "Price":"",
            "ImageId":"/sfc/servlet.shepherd/version/renditionDownload?rendition=ORIGINAL_Png&versionId=068f4000002yjYkAAI",
            "planId":"a0sf4000001u0CkAAI",
            "planRateType":"Composite",
            "RateBandTierPriceData":{  
               "Self":{  
                  "Price":345,
                  "Sequence":"1",
                  "Label":"Employee"
               },
               "Self + Spouse":{  
                  "Price":690,
                  "Sequence":"2",
                  "Label":"Employee + Spouse"
               },
               "Self + Child":{  
                  "Price":655.5,
                  "Sequence":"3",
                  "Label":"Employee + Child"
               },
               "Family":{  
                  "Price":1000.5,
                  "Sequence":"5",
                  "Label":"Family"
               }
            },
            "attributeCategories":{  
               ...
            }
         ]
      }
```

Did this article solve your issue?

Let us know so we can improve!

YesNo