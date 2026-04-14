---
title: "InsPolicyService:createRenewalPolicy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalpolicy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createRenewalPolicy

InsPolicyService:createRenewalPolicy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createRenewalPolicy

Use this service to create a renewal policy from an existing policy.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `createRenewalPolicy`

[](https://help.salesforce.com/s?language=en_US)

## How it Works

1.  The service accepts the `policyId` of the policy to be renewed.
    
    Note
    
    The service passes `userInputs` to determine additional rating factors for recalculating the price. Also, the service uses the `additionalFields` node to populate additional fields on the policy object, which otherwise aren’t part of this service.
    
2.  The service checks for the effective date and expiration date of the renewed policy. If not provided, the service computes these dates using the following logic:
    
    -   Effective date = Expiration date of original policy + 1 day
        
    -   Expiration date = Effective date of new policy + Term of the new policy
        
3.  Reprices the policy product using `aggByKey` and `includeInputKey` options.
    
4.  The service uses `includePaymentSchedule` and `includeRevenueSchedule` to determine whether the payment schedule and the revenue schedule must be created on renewed policy. If no options are specified, then the same settings are inherited from the previous policy.
    
5.  The service creates a policy and marks it as renewed policy.
    

Note

The service additionally supports renewal of policies where the original policy version has a duration of less than 365 days, or less than 366 days in a leap year. However, on renewal the policy duration is 365 days, or 366 days for a leap year. See [Considerations and Limitations for Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_limitations_for_insurance_policies.htm&language=en_US&type=5).

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

If no userInputs are provided, the renewal service takes the existing policy's information and reproduces it in the renewed policy.

 |
| 

`additionalFields`

 | 

Optional

The key-value pairs of the additional fields that aren’t a part of this service. These fields populate on the policy object.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

Note All the remote options used in `InsProductService:repriceProduct` can also be used with this service.

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`renewalExpirationDate`

 | 

Optional

The expiration date of the renewed policy. If not provided, the value is set using the following logic:

Effective date of new policy + Term of new policy

 |
| 

`renewalEffectiveDate`

 | 

Optional

The effective date of the renewed policy. If not provided, the value is computed using the following logic:

Expiration date of existing policy + 1 day

If you're using the Insurance Industries Extension package, the timestamp value in the `renewalEffectiveDate` option is ignored. Instead, the effective date timestamp value is set to 12:00 a.m. of the selected effective date, and the expiration date value is set to 11:59 p.m. for the selected expiration date. The timestamp is set by using the user's specified timezone.

 |
| 

`aggByKey`

 | 

Required

`PRODUCT.instanceKey`

The service sends this option as an input to the calculation procedure, which uses it to complete the calculation with aggregation.

For example, an auto insurance policy has multiple drivers attached to each insured vehicle. The insured vehicle has a separate instanceKey for each instance in the policy. The aggByKey takes all the instance keys for the vehicles and creates an array of coverage premiums per instanceKey. This array is passed to the calculation procedure so that premiums are calculated correctly.

The service uses this value to reprice the policy.

 |
| `calculateTaxesAndFees` | 

Optional.

Default value is `true`.

Set to `true` to calculate taxes and fees.

 |
| 

`createTransaction`

 | 

Optional.

True or False

Defaults to False.

If true, the service creates a transaction that is used by the revenue schedule services.

 |
| 

`includeInputKeys`

 | 

Required

A string of comma-separated key-value pairs that the service passes into and out of the calculation procedure.

These key-value pairs are included in the output product object within the `CalculatedPriceData` object. They're there to help you parse the calculation results.

Only keys used by the calculation procedure have a value in the results.

The service uses `includeInputKeys` to reprice the policy.

 |
| 

`includePaymentSchedule`

 | 

Optional

If true, the service creates a payment schedule on renewed policy. If no value is provided, the service creates a payment schedule on renewed policy only if it's present for the original policy.

 |
| 

`includeRevenueSchedule`

 | 

Optional

If true, the service creates a revenue schedule on renewed policy. If no value is provided, the services create a payment schedule on renewed policy only if it's present for the original policy.

 |
| 

`paymentCalculationMethod`

 | 

Required, if the value of `includePaymentSchedule` is true.

Overrides the policy's `Premium Calculation Method` value.

 |
| 

`paymentFrequency`

 | 

Required if the value of `includePaymentSchedule` is true.

Overrides the policy's `PremiumFrequency` value.

 |
| 

`paymentType`

 | 

Required if the value of `includePaymentSchedule` is true.

Overrides the policy's `Premium Payment Type` value.

 |
| 

`ratingDate`

 | 

Determines the rating procedure for pricing of the renewed policy. If not provided, then pricing is done based on the effective date of the renewed policy.

Note You can't pass a specific time for ratingField as the field type is Date. So, the rating date timestamp defaults to 12:00 am.





 |
| 

`term`

 | 

Optional

The term of the policy. It help calculates `renewalExpirationDate`, if not provided in the remote options. InsPolicyService:createRenewalPolicy supports only annual policy terms..

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
    ],
   "additionalFields": {
      "BillingName": "John Smith",
      "Description": "This is a renewal quote",
      "Phone": "123456789"
    }
}    
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's an example of the output JSON:

```json
{
  "snapshotId": [
    "00P5w00001fKlqEEAS"
  ],
  "InsurancePolicy": [
    "0YT5w000000Y8tTGAS"
  ]
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo