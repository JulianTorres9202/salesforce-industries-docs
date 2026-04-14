---
title: "InsPolicyService:createPaymentSchedule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpaymentschedule.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:createPaymentSchedule

InsPolicyService:createPaymentSchedule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:createPaymentSchedule

The InsPolicyService:createPaymentSchedule service creates a payment schedule (and optionally an initial payment transaction) for the target policy. This applies to Insurance Policy object only. The Policy (Asset) object is not supported.

[](https://help.salesforce.com/s?language=en_US)

Class: InsPolicyService

Method: createPaymentSchedule

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes an InsurancePolicy ID and creates a payment schedule using the policy's information and the optional parameters.
    
2.  If the policy's **Original Policy Id** already has an existing payment schedule, the service returns an error message.
    
3.  If there's an initial payment, an **Insurance Policy Transaction** is created.
    
4.  When saving the payment schedule, the records are linked to the policy's **Original Policy Id**.
    
5.  The payment schedule is added to the JSON result.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| `coolingOffPeriod` | 

Optional

The number of days you can delay the first payment schedule entry. ​ ​

With cooling off period, the first payment schedule date of the policy is calculated as the effective date + the number of days.

For example, there is a monthly payment frequency where the effective date is Jan 5, and the first payment schedule date is Jan 5. If we apply a cooling off period of 14 days, the first payment schedule entry changes from Jan 5 to Jan 19. The remaining monthly payment schedule dates remain unchanged.

Note Cooling off period must be in range of 1 to 28 days from the start date of the policy.





 |
| 

`getDataCustomClassName`

 | 

Optional.

The custom class to use to retrieve the Insurance Policy record.

Default is **GetInsurancePolicy**.

 |
| 

`getDataDRBundleName`

 | 

Optional.

The Omnistudio Data Mapper used to retrieve the payment schedule.

 |
| 

`initialPaymentRule`

 | 

Optional.

The payment rule used for the initial payment. Example: Days, Months or Percentage.

 |
| 

`initialPaymentTransactionName`

 | 

Optional.

The transaction name.

Default is to use the same value as `initialPaymentTransactionType`.

 |
| 

`initialPaymentTransactionType`

 | 

Optional.

The transaction type.

Default is **Premium Charge**.

 |
| 

`initialPaymentValue`

 | 

Optional.

The **Percentage** value, or the number of **Months** or **Days**.

Required if `initialPaymentRule` is used.

 |
| 

`paymentCalculationMethod`

 | 

Optional.

Overrides the policy's **Premium Calculation Method** value.

 |
| 

`paymentFrequency`

 | 

Optional.

Overrides the policy's **Premium Frequency** value.

 |
| 

`paymentStartDate`

 | 

Optional.

The date of the first payment schedule entry.

Default is the policy's effective date.

 |
| 

`paymentType`

 | 

Optional.

Overrides the policy's **Premium Payment Type** value.

 |
| 

`policyId`

 | 

Required.

The Id of the InsurancePolicy used to create the payment schedule.

 |
| 

`postPaymentDataCustomClassName`

 | 

Optional.

The custom class to use to save the payment schedule.

Default is  **PostInsurancePolicyPaymentSchedule**

 |
| 

`postPaymentDataDRBundleName`

 | 

Optional.

The Data Mapper used to save the payment schedule.

 |
| 

`postPaymentSchedule`

 | 

Optional.

True if the payment schedule records will be saved.

Default is `True`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Outputs

| 
Output

 | 

Description

 |
| --- | --- |
| 

`paymentSchedule`

 | 

The list of **Insurance Policy Payment Schedule Entry** records.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

```json
{
    "policyId": "0YT5w000000UHv6GAG",
    "paymentFrequency": "Monthly",
    "paymentCalculationMethod": "Daily",
    "paymentType": "Advanced",
    "paymentStartDate": "1/1/2020",
    "initialPaymentRule": "Percentage",
    "initialPaymentValue": "10",
    "initialPaymentTransactionType": "Premium Charge",
    "initialPaymentTransactionName": "",
    "postPaymentSchedule": "true"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

```json
{
  "output": {
    "paymentSchedule": [
      {
        "totalAmount": 571.5,
        "toDelete": null,
        "taxAmount": 51.5,
        "scheduleDate": "2020-06-21",
        "premiumAmount": 515,
        "insTransaction": {
          "type": "Premium Charge",
          "transactionNumber": null,
          "transactionDate": null,
          "totalAmount": 571.5,
          "taxAmount": 51.5,
          "postDate": null,
          "name": "Premium Charge",
          "Id": null,
          "feeAmount": 5,
          "amount": 515,
          "additionalInfo": null
        },
        "Id": null,
        "feeAmount": 5
      },
      {
        "totalAmount": 2578.79,
        "toDelete": null,
        "taxAmount": 232.38,
        "scheduleDate": "2020-09-21",
        "premiumAmount": 2323.85,
        "insTransaction": null,
        "Id": null,
        "feeAmount": 22.56
      },
      {
        "totalAmount": 1268.27,
        "toDelete": null,
        "taxAmount": 114.29,
        "scheduleDate": "2020-12-21",
        "premiumAmount": 1142.88,
        "insTransaction": null,
        "Id": null,
        "feeAmount": 11.1
      },
      {
        "totalAmount": 1296.44,
        "toDelete": null,
        "taxAmount": 116.83,
        "scheduleDate": "2021-03-21",
        "premiumAmount": 1168.27,
        "insTransaction": null,
        "Id": null,
        "feeAmount": 11.34
      }
    ],
    "errorCode": "INVOKE-200",
    "error": "OK"
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo