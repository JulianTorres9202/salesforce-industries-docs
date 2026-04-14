---
title: "InsPolicyService:modifyPaymentSchedule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__modifypaymentschedule.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:modifyPaymentSchedule

InsPolicyService:modifyPaymentSchedule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:modifyPaymentSchedule

Use this service to modify an existing payment schedule based on a new Premium Frequency.

Note

This service works with the Salesforce FSC InsurancePolicy object, not the Vlocity Policy (Asset) object.

[](https://help.salesforce.com/s?language=en_US)

Class: InsPolicyService

Method: modifyPaymentSchedule

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service accepts an insurance policy ID and the effective date of the policy's payment schedule change.
    
2.  If the policy's **Original Policy Id** has no existing payment schedule, the service returns an error message.
    
    To create a payment schedule, use `InsPolicyService: createPaymentSchedule`.
    
3.  The service uses the policy's **Premium Calculation Method**, **Payment Type**, **Standard Premium**, **Standard Fee**, and **Standard Tax** to generate a modified payment schedule. If `paymentFrequency` isn't provided as input, the service uses the policy's **Premium Frequency**.
    
4.  When saving the payment schedule, the service links records to the policy's **Original Policy Id**.
    
5.  The service adds the payment schedule to the JSON result.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`effectiveDate`

 | 

Required.

The date the modification takes effect.

 |
| 

`getDataCustomClassName`

 | 

Optional.

The custom class that retrieves the Insurance Policy record.

Default is `GetInsurancePolicy`. 

 |
| 

`getDataDRBundleName`

 | 

Optional.

The Omnistudio Data Mapper that retrieves the payment schedule.

 |
| 

`paymentFrequency`

 | 

The new **Premium Frequency** value for the payment schedule.

 |
| 

`policyId`

 | 

The ID of the **InsurancePolicy** with the payment schedule to modify.

 |
| 

`postPaymentDataCustomClassName`

 | 

Optional.

The custom class that saves the payment schedule.

The default value is `PostInsurancePolicyPaymentSchedule`.

 |
| 

`postPaymentDataDRBundleName`

 | 

Optional.

The Data Mapper that saves the payment schedule.

 |
| 

`postPaymentSchedule`

 | 

Optional.

`True` to save the payment schedule records.

The default value is `True`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

```json
{
    "policyId": "0YT6g000000MEPEGA4",
    "effectiveDate": "3/1/2021",
    "paymentFrequency": "Quarterly",
    "postPaymentSchedule": "false"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

```json
{
  "output": {
    "paymentSchedule": [
      {
        "totalAmount": 298.53,
        "toDelete": null,
        "taxAmount": 26.75,
        "scheduleDate": "2021-01-01",
        "premiumAmount": 267.53,
        "insTransaction": null,
        "Id": "a606g000000R1s7AAC",
        "feeAmount": 4.25
      },
      {
        "totalAmount": 269.64,
        "toDelete": null,
        "taxAmount": 24.16,
        "scheduleDate": "2021-02-01",
        "premiumAmount": 241.64,
        "insTransaction": null,
        "Id": "a606g000000R1s8AAC",
        "feeAmount": 3.84
      },
      {
        "totalAmount": 433.36,
        "toDelete": null,
        "taxAmount": 38.84,
        "scheduleDate": "2021-03-15",
        "premiumAmount": 388.36,
        "insTransaction": null,
        "Id": null,
        "feeAmount": 6.16
      },
      ...
    ],
    "errorCode": "INVOKE-200",
    "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo