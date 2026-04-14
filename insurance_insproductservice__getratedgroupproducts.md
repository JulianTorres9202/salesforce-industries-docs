---
title: "InsProductService:getRatedGroupProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedgroupproducts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductService:getRatedGroupProducts

InsProductService:getRatedGroupProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductService:getRatedGroupProducts

This service is used only with small group products that use a census. The service allows the products to be kept with the product service.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsProductService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getRatedGroupProducts`

[](https://help.salesforce.com/s?language=en_US)

There are a couple of different ways you can use this service, depending on how you use the accountId, censusId, and userInput options. Here are a few important concepts you'll need to keep in mind:

[](https://help.salesforce.com/s?language=en_US)

-   You can use either an accountId or censusId, or both, to pull in a census;
    
-   If you use an accountId and no censusId is specified, the system census is used, where the status is Active and the census type is Group;
    
-   If you use a censusId, it overrides any census associated with the accountId;
    
-   userInputs from input map will be taken, but if there are no userInputs in the input map, the service will generate them from census members;
    
-   However, you can use userInputs from the getRatedProducts service, if needed.
    

[](https://help.salesforce.com/s?language=en_US)

Note

`getRatedProducts` contains the inputs needed by the rating procedure, as mapped in the attributes of the product, including its associated coverage specs; insured item specs; insured party specs; and rating fact specs.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service gets the active Group census, provided via `censusId`. Or you can pass the service an `accountId` and the service uses the `accountId` to get a census of type System.
    
    Alternately, it can take `userInputs`, if there is no censusId or accountId provided.
    
    If you provide both `userInputs` and `censusId` or `accountId`, the service merges the `userInputs` with generated `userInputs` from the Group census if the remote option `mergeUserInputs` is set to true (default = false).
    
2.  Gets the Account's Rating type and accepts the Product Type as an input filter.
    
3.  Calls `getRatedProduct` for pricing, and returns plans. The number of plans returned per page is based on the `pageSize` option (described below).
    
4.  Pulls in `employerContribution`  from the census and then uses the price from `getRatedProduct` to calculate employer contribution for each product.
    
5.  Puts a node in the JSON root for `EmployerContribution`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

Note

All of the remote options used in the getRatedProducts service may also be used here.

| 
Option

 | 

Description

 |
| --- | --- |
| 

`accountId`

 | 

Optional.

ID of account. Must use either this or censusId.

 |
| 

`censusId`

 | 

Optional.

Id of census. Must use either this or accountId.

 |
| 

`productCategory`

 | 

Either Medical, Dental, Vision, or Life.

Filters above input by Product.Type, GroupClass.Type,

GroupClassContribution.ProductCategory

 |
| 

`includeContributionInUserInput`

 | 

Boolean.

If true, the generated `userInputs`, based on the `accountId` or `censusId`, will include the employer contributions per member, and the following sample attributes will be added:

-   Dental.contributionAmount
    
-   Medical.contributionPercent
    

 |
| 

`excludeContributionInOutput`

 | 

Boolean.

If true, `employerContributions` is not returned in the outputJSON

 |
| 

`omitChildren`

 | 

`true` or `false`

Set this option to true only if you also set `omitRating` to `true`. This returns products without pricing.

 |
| 

`omitRating`

 | 

`true` or `false`

If `true`, the service returns products without pricing.

 |
| 

`rateType`

 | 

String value, either `Age` or `Composite`.

Typically, if census size is 20 or below use Age; if greater, use Composite.

Pass through to Integration Procedure and accessed via `%options.rateType%`

 |
| 

`pageSize`

 | 

Number of plans to load per OmniScript page.

Important

It is strongly recommended to set this value to 9 to avoid any loading issues.







 |
| 

[](https://help.salesforce.com/s?language=en_US)`validateCoverageSelection`

 | 

`true` or `false`

Set to `true` if have validation rules that you need the service to run.

 |
| 

`mergeUserInputs`

 | 

`true` or `false`

Default = `false`.

Merges the `userInputs` with generated `userInputs` from the Group census when set to `true`.

See Input JSON, below, for more info.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

Optionally, you can provide `userInputs` nodes here, such as if you're using the `mergeUserInputs` remote option. In this case, a unique instance key must be defined in the `userInput` and in the census member record (it must be the same key) so the service can match each `userInput` with each census member record. (It's a good idea to use the census member ID as the instance key.)

```
"userInputs": [
{
"SG-Census-RF.SG_CM_Calculate": "true",
"SG-Census-RF.SG_CM_Age": 48,
"SG-Census-RF.Id": "a57g00000009i0wAAA",
"SG-Census-RF.SG_CM_Zip": "48005",
"SG-Census-RF.instanceKey": "a57g00000009i0wAAA"
},
{
"SG-Census-RF.SG_CM_Calculate": "true",
"SG-Census-RF.SG_CM_Age": 32,
"SG-Census-RF.Id": "a57g00000009i0rAAA",
"SG-Census-RF.SG_CM_Zip": "48005",
"SG-Census-RF.instanceKey": "a57g00000009i0rAAA"
}
]
}
```

You must also populate the `CensusMember.AttributeSelectedValue__c` in the census member field with a JSON similar to this, with the same instance key:

```
{
"SG_empOnlyCount": "",
"SG_empSpouseCount": "",
"SG_empChildCount": "",
"SG_empFamilyCount": "",
"SG_CM_MemberClass": null,
"SG_CM_Age": 48,
"SG_CM_State": null,
"SG_CM_Gender": null,
"SG_CM_Smoker": false,
"SG_CM_IsPrimary": false,
"SG_CM_IsSpouse": false,
"SG_CM_DOB": null,
"SG_CM_Relationship": null,
"SG_CM_Zip": null,
"Id": null,
"SG_CM_MemberType": null,
"SG_CM_Calculate": true,
"instanceKey":”a57g00000009i0wAAA”
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns `employerContributions` based on the `productId`. Results are formatted as per the JSONResult object.

-   If the contribution type is Amount, only the `contributionAmount` attribute is returned
    
-   If the contribution type is Percent, `contributionPercent` is returned
    
-   If the Product Price is available, the computed `contributionAmount` is returned
    

```
{
  "employerContributions": {
    "01tf4000002U25LAAS": [
      {
        "contributionAmount": 363.999,
        "contributionPercent": 30,
        "Member.Id": "a3ef4000000mPIaAAM"
      },
      {
        "contributionAmount": 363.999,
        "contributionPercent": 30,
        "Member.Id": "a3ef4000000mPIbAAM"
      }
    ],
    "01tf4000002U25KAAS": [
      {
        "contributionAmount": 100,
        "Member.Id": "a3ef4000000mPIaAAM"
      },
      {
        "contributionAmount": 100,
        "Member.Id": "a3ef4000000mPIbAAM"
      }
    ]
  },
  "result": {
    "totalSize": 2,
    "records": [
      {
        "uiStates": {},
        "nameResult": {
          "childProducts": {
            "totalSize": 2,
            "records": [
              {
                "uiStates": {},
                "nameResult": {},
                "messages": [],
                "fields": {
                  "pciId": "a2mf4000000lTZiAAM",
                  "productId": "01tf4000002U25MAAS",
                  "TotalInsuredFormula__c": null,
                  "Term__c": "Annual",
                  "PricingFormula__c": null,
                  "IsConfigurable__c": false,
                  "RecordTypeName__c": "RatingFactSpec",
                  "PricingSource__c": null,
                  "ImageId__c": null,
                  "Tier__c": null,
                  "IsRecommended__c": false,
                  "RateBandId__c": null,
                  "SubType__c": null,
                  "Type__c": null,
                  "MarketSegment__c": null,
                  "LineOfBusiness__c": null,
                  "ProductCode": "RF0",
                  "Family": null,
                  "Description": null,
                  "Name": "censusRatingFact",
                  "Id": "01tf4000002U25MAAS"
                },
                "displaySequence": 1,
                "actions": {}
              },
              {
                "uiStates": {},
                "nameResult": {},
                "messages": [],
                "fields": {
                  "pciId": "a2mf4000000lTZjAAM",
                  "productId": "01tf4000002U25NAAS",
                  "TotalInsuredFormula__c": null,
                  "Term__c": "Annual",
                  "PricingFormula__c": null,
                  "IsConfigurable__c": false,
                  "RecordTypeName__c": "RatingFactSpec",
                  "PricingSource__c": null,
                  "ImageId__c": null,
                  "Tier__c": null,
                  "IsRecommended__c": false,
                  "RateBandId__c": null,
                  "SubType__c": null,
                  "Type__c": null,
                  "MarketSegment__c": null,
                  "LineOfBusiness__c": null,
                  "ProductCode": "RF1",
                  "Family": null,
                  "Description": null,
                  "Name": "censusMemRatingFact",
                  "Id": "01tf4000002U25NAAS"
                },
                "displaySequence": 2,
                "actions": {}
              }
            ],
            "name": null,
            "messages": [],
            "description": null,
            "data": {
              "totalSize": null,
              "messages": [],
              "dataMap": {},
              "actions": {}
            },
            "actions": {}
          }
        },
        "messages": [],
        "fields": {
          "Price": "",
          "productId": "01tf4000002U25KAAS",
          "TotalInsuredFormula__c": null,
          "Term__c": null,
          "PricingFormula__c": null,
          "IsConfigurable__c": false,
          "RecordTypeName__c": "Product",
          "PricingSource__c": "AggOutput",
          "ImageId__c": null,
          "Tier__c": null,
          "IsRecommended__c": false,
          "RateBandId__c": null,
          "SubType__c": null,
          "Type__c": "Medical",
          "MarketSegment__c": null,
          "LineOfBusiness__c": null,
          "ProductCode": "rootProd",
          "Family": null,
          "Description": null,
          "Name": "rootProd",
          "Id": "01tf4000002U25KAAS",
          "RawPriceData": [
            {
              "calculationResults": [
                {
                  "ProcedureOutput": 1000,
                  "TheMatrix__Premium": "100",
                  "TheMatrix__PremiumRBSelf": "90",
                  "TheMatrix__PremiumRBSpouse": "110",
                  "ID": "0"
                },
                {
                  "ProcedureOutput": 1500,
                  "TheMatrix__Premium": "150",
                  "TheMatrix__PremiumRBSelf": "140",
                  "TheMatrix__PremiumRBSpouse": "160",
                  "ID": "1"
                },
                {
                  "ProcedureOutput": 2000,
                  "TheMatrix__Premium": "200",
                  "TheMatrix__PremiumRBSelf": "190",
                  "TheMatrix__PremiumRBSpouse": "210",
                  "ID": "2"
                },
                {
                  "ProcedureOutput": 1300,
                  "TheMatrix__Premium": "130",
                  "TheMatrix__PremiumRBSelf": "120",
                  "TheMatrix__PremiumRBSpouse": "240",
                  "ID": "3"
                },
                {
                  "ProcedureOutput": 2000,
                  "TheMatrix__Premium": "200",
                  "TheMatrix__PremiumRBSelf": "190",
                  "TheMatrix__PremiumRBSpouse": "210",
                  "ID": "4"
                },
                {
                  "ProcedureOutput": 1300,
                  "TheMatrix__Premium": "130",
                  "TheMatrix__PremiumRBSelf": "120",
                  "TheMatrix__PremiumRBSpouse": "240",
                  "ID": "5"
                }
              ],
              "aggregationResults": null
            }
          ],
          "CalculatedPriceData": {}
        },
        "displaySequence": -1,
        "actions": {}
      },
      {
        "uiStates": {},
        "nameResult": {
          "childProducts": {
            "totalSize": 2,
            "records": [
              {
                "uiStates": {},
                "nameResult": {},
                "messages": [],
                "fields": {
                  "pciId": "a2mf4000000lTZkAAM",
                  "productId": "01tf4000002U25MAAS",
                  "TotalInsuredFormula__c": null,
                  "Term__c": "Annual",
                  "PricingFormula__c": null,
                  "IsConfigurable__c": false,
                  "RecordTypeName__c": "RatingFactSpec",
                  "PricingSource__c": null,
                  "ImageId__c": null,
                  "Tier__c": null,
                  "IsRecommended__c": false,
                  "RateBandId__c": null,
                  "SubType__c": null,
                  "Type__c": null,
                  "MarketSegment__c": null,
                  "LineOfBusiness__c": null,
                  "ProductCode": "RF0",
                  "Family": null,
                  "Description": null,
                  "Name": "censusRatingFact",
                  "Id": "01tf4000002U25MAAS"
                },
                "displaySequence": 1,
                "actions": {}
              },
              {
                "uiStates": {},
                "nameResult": {},
                "messages": [],
                "fields": {
                  "pciId": "a2mf4000000lTZlAAM",
                  "productId": "01tf4000002U25NAAS",
                  "TotalInsuredFormula__c": null,
                  "Term__c": "Annual",
                  "PricingFormula__c": null,
                  "IsConfigurable__c": false,
                  "RecordTypeName__c": "RatingFactSpec",
                  "PricingSource__c": null,
                  "ImageId__c": null,
                  "Tier__c": null,
                  "IsRecommended__c": false,
                  "RateBandId__c": null,
                  "SubType__c": null,
                  "Type__c": null,
                  "MarketSegment__c": null,
                  "LineOfBusiness__c": null,
                  "ProductCode": "RF1",
                  "Family": null,
                  "Description": null,
                  "Name": "censusMemRatingFact",
                  "Id": "01tf4000002U25NAAS"
                },
                "displaySequence": 2,
                "actions": {}
              }
            ],
            "name": null,
            "messages": [],
            "description": null,
            "data": {
              "totalSize": null,
              "messages": [],
              "dataMap": {},
              "actions": {}
            },
            "actions": {}
          }
        },
        "messages": [],
        "fields": {
          "Price": 1213.33,
          "productId": "01tf4000002U25LAAS",
          "TotalInsuredFormula__c": null,
          "Term__c": null,
          "PricingFormula__c": null,
          "IsConfigurable__c": false,
          "RecordTypeName__c": "Product",
          "PricingSource__c": "AggOutput",
          "ImageId__c": null,
          "Tier__c": null,
          "IsRecommended__c": false,
          "RateBandId__c": "a4Gf4000000kocZEAQ",
          "SubType__c": null,
          "Type__c": "Dental",
          "MarketSegment__c": null,
          "LineOfBusiness__c": null,
          "ProductCode": "rootProd2",
          "Family": null,
          "Description": null,
          "Name": "rootProd2",
          "Id": "01tf4000002U25LAAS",
          "RawPriceData": [
            {
              "calculationResults": [
                {
                  "ProcedureOutput": 800,
                  "TheMatrix__Premium": "100",
                  "TheMatrix__PremiumRBSelf": "90",
                  "TheMatrix__PremiumRBSpouse": "110",
                  "ID": "0"
                },
                {
                  "ProcedureOutput": 1200,
                  "TheMatrix__Premium": "150",
                  "TheMatrix__PremiumRBSelf": "140",
                  "TheMatrix__PremiumRBSpouse": "160",
                  "ID": "1"
                },
                {
                  "ProcedureOutput": 1600,
                  "TheMatrix__Premium": "200",
                  "TheMatrix__PremiumRBSelf": "190",
                  "TheMatrix__PremiumRBSpouse": "210",
                  "ID": "2"
                },
                {
                  "ProcedureOutput": 1040,
                  "TheMatrix__Premium": "130",
                  "TheMatrix__PremiumRBSelf": "120",
                  "TheMatrix__PremiumRBSpouse": "240",
                  "ID": "3"
                },
                {
                  "ProcedureOutput": 1600,
                  "TheMatrix__Premium": "200",
                  "TheMatrix__PremiumRBSelf": "190",
                  "TheMatrix__PremiumRBSpouse": "210",
                  "ID": "4"
                },
                {
                  "ProcedureOutput": 1040,
                  "TheMatrix__Premium": "130",
                  "TheMatrix__PremiumRBSelf": "120",
                  "TheMatrix__PremiumRBSpouse": "240",
                  "ID": "5"
                }
              ],
              "aggregationResults": {
                "AggOutput": 1213.33
              }
            }
          ],
          "CalculatedPriceData": {
            "AggOutput": 1213.33
          }
        },
        "displaySequence": -1,
        "actions": {}
      }
    ],
    "name": null,
    "messages": [],
    "description": null,
    "data": {
      "totalSize": null,
      "messages": [],
      "dataMap": {},
      "actions": {}
    },
    "actions": {}
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo