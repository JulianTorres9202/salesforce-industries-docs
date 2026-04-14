---
title: "Rate Products Invocable Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rate_products_invocable_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Rate Products Invocable Action

Rate Products Invocable Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Rate Products Invocable Action

Rates insurance products as part of the Group Benefits Rating business process.

This action is available in API version 59.0 and later.

## Supported REST HTTP Methods

**URI**

`/services/data/vXX.X/actions/standard/rateProducts`

**Formats**

JSON

**HTTP Methods**

GET, POST

**Authentication**

`Authorization: Bearer token`

## Inputs

| Input | Details |
| --- | --- |
| `aggregationKey` | 
**Type**

String

**Description**

Optional. The aggregation key to use to group aggregation results.

 |
| `effectiveDate` | 

**Type**

Date

**Description**

Optional. The date used to determine which expression set to use to rate products.

 |
| `inputKeysList` | 

**Type**

List

**Description**

Optional. A comma-delimited list of input keys from rating inputs to include in the individual rating

 |
| `insuranceRatingRequestId` | 

**Type**

ID

**Description**

The ID of the insurance rating request record to rate insurance products for.

 |
| `isIncludeInputs` | 

**Type**

Boolean

**Description**

Optional. A Boolean value that indicates whether to include rating inputs in the individual rating results.

 |
| `ratingInputs` | 

**Type**

String

**Description**

A string that specifies rating inputs and rating details for each relevant product.

 |

## Outputs

None

## Usage

Sample Request

```json
{
   "inputs":[{
      "ratingInputs": "{\"136DI00000000HI\": {\"ratingInputs\": [{\"ProductCode\": \"SampleProductCode\", \"ProductName\": \"SampleProductName\", \"productKey\": \"01tDI000000ENUTYA4\", \"ratingType\": null, \"sfdcUniqueId\": \"0r6DI00000000y4YAA\", \"Age\": 0, \"primaryMemberId\": \"0r6DI00000000y4YAA\", \"Gender\": \"Male\" }], \"productInfo\": \"01tDI000000ENUTYA4_01tDI000000ENUTYA4\", \"configurationName\": \"ExpressionSetName\" }}",
      "aggregationKey": "primaryMemberId",
      "effectiveDate": "07/27/2023",
      "insuranceRatingRequestId": "8zkDI00000000MDYAY"
   }]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo