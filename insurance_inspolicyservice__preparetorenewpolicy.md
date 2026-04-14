---
title: "InsPolicyService:prepareToRenewPolicy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetorenewpolicy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:prepareToRenewPolicy

InsPolicyService:prepareToRenewPolicy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:prepareToRenewPolicy

Use this service to calculate the amount required for renewing an existing policy. This service returns renewal premium, taxes, and fees, or the renewal policy JSON without creating a policy.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `prepareToRenewPolicy`

[](https://help.salesforce.com/s?language=en_US)

## How it Works

[](https://help.salesforce.com/s?language=en_US)

1.  The service accepts the `policyId` of the policy to be renewed.
    
2.  The service checks for the effective date and expiration date of the renewed policy. If not provided, the service computes these dates using the following logic:
    
    -   Effective date = Expiration date of original policy + 1 day
        
    -   Expiration date = Effective date of new policy + Term of the new policy
        
3.  Reprices the policy product using `aggByKey` and `includeInputKey` options.
    
4.  Uses `getPolicyJson` to determine whether only renewal amount components must return or full policy JSON is sent in the response.
    

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

[](https://help.salesforce.com/s?language=en_US)The details of the products associated with the policy. For any product, the target format for the `userInputs` object is obtained from the service listing in the API tab of the product view. The object keys are in the format `ProductCode.AttributeCode` where the `ProductCode` is code of the product, associated coverage specs, insured item specs, or rating facts.

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

`aggByKey`

 | 

Required

`PRODUCT.instanceKey`

The service sends this option as an input to the calculation procedure, which uses it to complete the calculation with aggregation.

For example, an auto insurance policy has multiple drivers attached to each insured vehicle. The insured vehicle has a separate instanceKey for each instance in the policy. The `aggByKey` takes all the instance keys for the vehicles and creates an array of coverage premiums per instanceKey. This array is passed to the calculation procedure so that premiums are calculated correctly.

The service uses this option to reprice the policy.

 |
| 

`calculateTaxesAndFees`

 | 

Optional

`true` or `false`

Set to true to calculates taxes and fees on the renewed policy.

 |
| 

`includeInputKeys`

 | 

Required

A string of comma-separated key-value pairs that the service passes into and out of the calculation procedure.

These key-value pairs are included in the output product object within the `CalculatedPriceData` object. They're there to help you parse the calculation results.

The service uses this option to reprice the policy.

 |
| 

`getPolicyJson`

 | 

Optional

A boolean flag to determine whether only renewal amount components must return in response or full policy JSON must return.

 |
| 

`ratingDate`

 | 

Determines the rating procedure for repricing the policy. If not provided, pricing is done based on the effective date of the modified policy.

Note You can't pass a specific time for ratingField as the field type is Date. So, the rating date timestamp defaults to 12:00 am.





 |
| 

`renewalEffectiveDate`

 | 

Optional

The effective date of the renewed policy. If not provided, the value is computed using the following logic:

Expiration date of existing policy + 1 day

 |
| 

`renewalExpirationDate`

 | 

Optional

The expiration date of the renewed policy. If not provided, the value is set using the following logic:

Effective date of new policy + Term of the new policy

 |
| 

`term`

 | 

Optional

The term of the policy. It help calculates `renewalExpirationDate`, if not provided in the remote options. InsPolicyService:prepareToRenewPolicy supports only annual policy terms.

 |
| 

`useLocalTimezone`

 | 

True or False

The default value is true.

When the value is set as true, the service uses the local timezone in which the policy is created.

When the value is set as false, the services uses GMT as the timezone.

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
    ]
}  
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's an example of the output JSON:

```json
{
  "totalFeeForTermDiff": -0.07,
  "totalTaxForTermDiff": 0,
  "totalPremiumForTermDiff": -2.73,
  "newFeeForTerm": 24.93,
  "newTaxForTerm": 0,
  "newPremiumForTerm": 997.27,
  "newFee": 25,
  "newTax": 0,
  "newStandardPremium": 1000
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo