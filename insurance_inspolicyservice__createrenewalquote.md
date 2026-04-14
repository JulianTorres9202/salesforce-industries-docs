---
title: "InsPolicyService:createRenewalQuote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalquote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createRenewalQuote

InsPolicyService:createRenewalQuote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createRenewalQuote

Use this service to create a renewal quote for an existing policy.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)Method: `createRenewalQuote`

[](https://help.salesforce.com/s?language=en_US)

## How it Works

1.  The service accepts the `policyId` of the policy to be renewed.
    
    Note
    
    The service passes `userInputs` to determine additional rating factors for recalculating the price. Also, the service uses the `additionalFields` node to populate additional fields on the quote object, which otherwise aren’t part of this service.
    
2.  The service checks for the effective date and expiration date of the renewed policy. If not provided, the service computes these dates using the following logic:
    
    -   Effective date = Expiration date of original policy + 1 day
        
    -   Expiration date = Effective date of new policy + Term of the new policy
        
3.  Reprices the policy product using `aggByKey` and `includeInputKey` options.
    
4.  The service creates an Opportunity record using the `OpportunityDetails JSON` node from the input. See sample input JSON. This node accepts only these three mandatory fields:
    
    -   Name
        
    -   StageName
        
    -   CloseDate
        
    
    Note Additional opportunity fields cannot be included in this node. However, you can update the opportunity record with additional details after the renewal quote is generated.
    
5.  The service creates a quote of type 'Renewal' and links it to the opportunity record created in the previous step.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`policyId`

 | 

Required

The ID of the policy that is to be renewed.

 |
| 

`userInputs`

 | 

Optional

The details of the products associated with the policy. For any product, the target format for the `userInputs` object is obtained from the service listing in the API tab of the product view. The object keys are in the format `ProductCode.AttributeCode` where the ProductCode is code of product, associated coverage specs, insured item specs, or rating facts.

 |
| 

`additionalFields`

 | 

Optional

The key-value pairs of the additional fields that aren’t a part of this service. These fields populate on the quote object.

 |
| 

`opportunityDetails`

 | 

The details of renewal opportunity, which is linked to the renewal quote. If this node isn’t present, then the service takes up the opportunity details from the opportunity linked to the source quote of the original policy.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`renewalEffectiveDate`

 | 

Optional

Effective date of the renewed policy. If not provided, the value is computed using the following logic:

Expiration date of existing policy + 1 day

 |
| 

`renewalExpirationDate`

 | 

Optional

Expiration date of the renewed policy. If not provided, the value is set using the following logic:

Effective date of new policy + Term of new policy

 |
| 

`term`

 | 

Optional

The term of the policy. It help calculates `renewalExpirationDate`, if not provided in the remote options. InsPolicyService:createRenewalQuote supports only annual policy terms.

 |
| 

`pricebook`

 | 

Optional

The name of the `PriceBook2` record assigned to `Quote.Pricebook2Id`. The default is standard.

 |
| 

`aggByKey`

 | 

Required

`PRODUCT.instanceKey`

The service sends this option as an input to the calculation procedure, which uses it to complete the calculation with aggregation.

For example, an auto insurance policy has multiple drivers attached to each insured vehicle. The insured vehicle has a separate instanceKey for each instance in the policy. The `aggByKey` takes all the instance keys for the vehicles and creates an array of coverage premiums per `instanceKey`. This array is passed to the calculation procedure so that premiums are calculated correctly.

The service uses this option to reprice the policy.

 |
| 

`includeInputKeys`

 | 

Required

A string of comma-separated key-value pairs that the service passes into and out of the calculation procedure.

These key-value pairs are included in the output product object within the `CalculatedPriceData` object. They're there to help you parse the calculation results.

Only keys used by the calculation procedure have a value in the results.

[](https://help.salesforce.com/s?language=en_US)The service uses this option to reprice the policy.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's an example of the input JSON:

```json
{
   "policyId": "0YT5w000000Y8MNGA0",
   "userInputs": [
      {
        "DRIVER.instanceKey": "Bob Jones",
        "DRIVER.LN": "Jones",
        "DRIVER.GENDER": "Male",
        "DRIVER.FN": "Bobby",
        "DRIVER.AGE": 30,
        "AUTO.instanceKey": "2018 Audi A3",
        "AUTO.autoYear": 2018,
        "AUTO.autoModel": "A4",
        "perAccident": 500
      }
    ],
   "additionalFields": {
      "BillingName": "John Smith",
      "Description": "This is a renewal quote",
      "Phone": "123456789"
    },
    "OpportunityDetails": {
      "Name": "Renewal Opportunity",
      "StageName": "Qualification",
      "CloseDate": "2023-04-04"
    }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The `quoteId` and `opportunityId` of the renewal quote.

Here's an example of the output JSON:

```json
{
  "quoteId": "0Q0B0000000A0YEKA0",
  "opportunityId": "006B0000006zdiAIAQ",
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo