---
title: "Generate User Inputs Invocable Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_generate_user_inputs_invocable_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Generate User Inputs Invocable Action

Generate User Inputs Invocable Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Generate User Inputs Invocable Action

Generates user inputs and fact ratings.

This action is available in API version 59.0 and later.

## Supported REST HTTP Methods

**URI**

`/services/data/vXX.X/actions/standard/generateUserInputs`

**Formats**

JSON

**HTTP Methods**

GET, POST

**Authentication**

`Authorization: Bearer token`

## Inputs

| Input | Details |
| --- | --- |
| `account` | 
**Type**

Account sObject

**Description**

Optional. The account record that the Omnistudio Data Mapper fetches field values from.

 |
| `contractGroupPlanId` | 

**Type**

ID

**Description**

Optional.The ID of the group plan record used to get group class contribution details.

 |
| `effectiveDate` | 

**Type**

Date

**Description**

Optional. The date used to determine which group class contribution details to use to generate user inputs. Required if Add Group Class Contribution is specified.

 |
| `fscNamespace` | 

**Type**

String

**Description**

The namespace of the FSC package.

 |
| `groupCensus` | 

**Type**

Group Census sObject

**Description**

Optional. The group census record that the Data Mapper fetches field values from.

 |
| `groupCensusMembers` | 

**Type**

List

**Description**

Optional. A collection of group census member records that the Data Mapper can fetch rating facts from.

 |
| `groupBenefitPlanProductCategory` | 

**Type**

String

**Description**

Optional. Specifies the product category to use to get the group class contribution details. Valid values include:

-   Medical
    
-   Dental
    
-   Vision
    
-   Medical Savings Account
    
-   Life
    
-   Retirement
    

 |
| `insuranceRatingRequestId` | 

**Type**

String

**Description**

Optional. The ID of the insurance rating request record.

 |
| `isAddGroupContribution` | 

**Type**

Boolean

**Description**

A Boolean value that indicates whether the group class contribution is added to user inputs.

 |
| `isMemberLevelPremium` | 

**Type**

Boolean

**Description**

Optional. A Boolean value that indicates whether to allocate contributions for subscribers and dependents based on group class contribution details. Required if Add Group Class Contribution is specified. The default value is false and group class contributions for dependents are the same as subscribers.

 |
| `memberSpecificAttributes` | 

**Type**

String

**Description**

Optional. A JSON string of attributes to be added at the individual group census member level.

 |
| `mode` | 

**Type**

String

**Description**

Optional. Identifies the type of flow that is calling the action. Valid values are:

-   quote
    
-   enrollment
    

Required if Add Group Class Contribution is specified.

 |
| `product2Id` | 

**Type**

String

**Description**

Optional. The ID of the product2 record to use to get the group class. Required if Add Group Class Contribution is specified.

 |
| `ratingFactProduct` | 

**Type**

List

**Description**

The product2 record that indicates which DataRaptors are used and that determines the product code prefix used for output.

 |
| `userInput` | 

**Type**

String

**Description**

Optional. A JSON string of user inputs.

 |

## Outputs

| Output | Details |
| --- | --- |
| `userInputs` | 
**Description**

A JSON string that includes the generated user inputs and rating facts.

 |

## Usage

Sample Request

```json
{
"inputs": [{
   "isAddGroupContribution" : false,
   "ratingFactProducts": [{"Id": "01tDI000000ENBeYAO", 
                            "vlocity_ins__DRBundleName__c": "TransformCensusMemberRatingFactsStd",
                            "ProductCode" : "LG-groupCensus-RF"}],
   "account": {"Id": "001DI000002fpqMYAQ",
               "Name": "Account Name"},
   "groupCensus": {"Id": "0rfDI00000000huYAA", 
                   "Name": "Quote Name"},
   "groupCensusMembers" : [{"Id": "0r6DI000000004tYAA",
                            "Gender": "Male"}],
   "userInput": "{\"sampleKey\": \"sampleValue\"}"
   }]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo