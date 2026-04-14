---
title: "InsQuoteService:getQuoteDetail"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:getQuoteDetail

InsQuoteService:getQuoteDetail[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:getQuoteDetail

Use this service to get all of the quote details as JSON.

[](https://help.salesforce.com/s?language=en_US)

This service works well for flows that take a saved quote and create either an insurance policy or a health plan from it.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getQuoteDetail`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes a `quoteId` and finds the quote.
    
2.  The service returns JSON that includes these key: values:
    
    -   [](https://help.salesforce.com/s?language=en_US)`quoteDetails`: Quote field values
        
        Includes quote field values with attributes.
        
    -   [](https://help.salesforce.com/s?language=en_US)`insuredItems`: Insured items and insured parties
        
        Includes InsuredItemSpec and InsuredPartySpec quote line details. (Not applicable for Vlocity Health.)
        
    -   [](https://help.salesforce.com/s?language=en_US)`productConfigurationDetail`: Product configurations
        
        Product JSON Structure Model
        

[](https://help.salesforce.com/s?language=en_US)

## Taxes and Fees

Here's how this service works:

-   The `taxAmount`, `TaxAmount__c`, `feeAmount`, `FeeAmount__c`, and `TotalAmount__c` fields are returned for each `QuoteLineItem`, if the fields aren’t null.
    
-   The `TotalTaxAmount__c`, `TotalFeeAmount__c`, and `TotalAmount__c` fields are returned for the quote, if the fields aren’t null.
    
-   The `totalTaxFeeAmount` = `TaxAmount__c` + `FeeAmount__c`
    

## Inputs

The service requires these inputs if the `isForExternal` remote option is set to true. Omit these inputs if `isForExternal` is blank or set to false.

| 
Option

 | 

Description

 |
| --- | --- |
| `action` | 

Required when isForExternal=true.

The service uses this value to create the Action node required for the external pricing API.

Possible values:

-   `submit`
-   `reprice`

 |
| `quoteId` | 

Required when isForExternal=true.

The ID of the quote to retrieve details for.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`action`

 | 

Required when isForExternal=true.

Indicates the action for the external server to do with the Quote.

Possible values:

-   `submit`
-   `reprice`

For submit, the `Quote`’s `sourceSystemIdentifer` is passed. For reprice, the `SourceSystemIdentifer` of the `Root QuoteLineItem` to be repriced or rated is passed.

 |
| 

`disableAttributeCategories`

 | 

Optional.

Show `attributeCategories` in output JSON.

If this flag is set to true, the `getQuoteDetail` service omits the `attributeCategory` node from the response and the `createPolicyVersion` service fails to create policy terms. To make sure that the `createPolicyVersion` service creates policy terms, set this flag to false.

 |
| 

`disableChildProducts`

 | 

Optional.

Show records under `childProduct` in output JSON.

 |
| 

`disableOptionalCoverages`

 | 

Optional.

When set to true, optional coverages don’t appear as part of a quote in an OmniScript.

 |
| 

`includeOriginalPlan`

 | 

If set to `true`, includes original products in a renewal.

Otherwise only replacement products are shown.

 |
| 

`includeOpportunity`

 | 

If set to `true`, return the quote's opportunity details in a separate JSON Node. The fields returned are determined by the field set `OpportunityDetail`.

The default value is `false`.

 |
| 

`instanceKey`

 | 

A unique identifier associated with the quote line item that's used to identify the instance of a product. The instanceKey is specified manually or system-generated.

 |
| 

`isMultiRoot`

 | 

`true` or `false`

Set to `true` for quotes that include more than one insurance product (plan).

For example, a quote that includes a health plan, a dental plan, and a vision plan must have this option set to `true` to return the details for the plans.

 |
| 

`isForExternal`

 | 

If set to `true`, the service returns the simplified JSON for ease of mapping to an external policy admin system.

 |
| 

`productCode`

 | 

Code of the product associated with a Quote Line Item.

 |
| 

`productSpecId`

 | 

Id of the product associated with a Quote Line Item.

 |
| 

`quoteId`

 | 

Required.

[](https://help.salesforce.com/s?language=en_US)The `QuoteId`, or the encrypted `QuoteId` if the request is for a customer.

 |
| 

`quoteLineItemId`

 | 

Id of the Quote Line Item. Returns only one Quote Line Item with the exact matching Id. If other filters are included in the request that don’t meet the returned item’s details, no items are returned.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```
{
  "quoteId": "...",
  "action":  "..."
}
```

Here's an example of the input JSON:

```
{
  "quoteId":"0Q06g0000009YA3CAM"
  "action": "submit"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON (Insurance)

The service returns a JSON that contains these nodes:

-   Insured parties and insured items
    
-   Quote details field set
    
-   Product configuration details
    

Tip

The `quoteDetail` field set exists on several objects, but the InsQuoteService:getQuoteDetail service reads only the field set on the Quote Line Item object when it builds the `productConfigurationDetail` node in the JSON response. Field sets on Product2 object are ignored by this service.

To reduce the payload size and improve the Omniscript performance, add or remove fields in the `quoteDetail` field set. A few Quote Line Item fields such as Product Name, Product Code, Product Id are included by default. We recommend you keep these sets unchanged because they’re essential to a quote.

```
{
  "productConfigurationDetail": {
    "records": [...]
    "totalSize": 1
  },
  "insuredItems": {
    "Driver": [{
        "instanceKey": "Joan Smith",
        "isPrimary": false,
        "isParent": false,
        "LN": "Smith",
        "AGE": 20,
        "FN": "Joan",
        "GENDER": "Female",
        "FirstName": "Joan",
        "LastName": "Smith"
      },
      {
        ...
      }
    ],
    "Auto": [{
        "instanceKey": "2015 Lexus LX250",
        "autoAntiTheft": true,
        "est_annual_mileage": "1-10000",
        "autoLicNum": "Lexus",
        "autoModel": "LX250",
        "autoYear": 2015,
        "BodyClass": "Sedan/Saloon",
        "VehicleType": "PASSENGER CAR",
        "isPrimary": true
        "isParent": false,
      },
      {
        ...
      }
    ]
  },
  "quoteDetail": {
    "attributes": {
      "type": "Quote",
      "url": "/services/data/v43.0/sobjects/Quote/0Q01I000000qeWLSAY"
    },
    "ins_daily4__EffectiveDate__c": "2018-07-27",
    "ins_daily4__TotalSumInsured__c": 0,
    "AccountId": "0011I00000QknfjQAB",
    "ins_daily4__RootItemTotal__c": 0,
    "Id": "0Q01I000000qeWLSAY"
  },
  "error": "OK"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON (Health)

The service returns a JSON that contains these nodes:

-   Quote details field set
    
-   Product configuration details
    

```
{
  "productConfigurationDetail": {
    "records": [...]
    "totalSize": 1
  },
  "quoteDetail": {
    "attributes": {
      "type": "Quote",
      "url": "/services/data/v43.0/sobjects/Quote/0Q01I000000qeWLSAY"
    },
    "ins_daily4__EffectiveDate__c": "2018-07-27",
    "ins_daily4__TotalSumInsured__c": 0,
    "AccountId": "0011I00000QknfjQAB",
    "ins_daily4__RootItemTotal__c": 0,
    "Id": "0Q01I000000qeWLSAY"
  },
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo