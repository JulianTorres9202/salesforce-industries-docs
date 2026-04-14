---
title: "InsPolicyService:getPaymentSchedule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getpaymentschedule.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getPaymentSchedule

InsPolicyService:getPaymentSchedule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getPaymentSchedule

The InsPolicyService:getPaymentSchedule service returns the payment schedule of the InsurancePolicy. The Policy (Asset) object is not supported.

[](https://help.salesforce.com/s?language=en_US)

Class: InsPolicyService

Method: getPaymentSchedule

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service retrieves the `InsurancePolicyPaymentScheduleEntry__c` records of the InsurancePolicy Id.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`getDataCustomClassName`

 | 

Optional.

The custom class used to retrieve the payment schedule.

Default is **GetInsurancePolicyPaymentSchedule**.

 |
| 

`getDataDRBundleName`

 | 

Optional.

The Omnistudio Data Mapper used to retrieve the payment schedule.

 |
| 

`policyId`

 | 

Required.

The Id of the **InsurancePolicy** for which this service retrieves the payment schedule.

 |
| 

`returnSObject`

 | 

Optional.

True if the `InsurancePolicyPaymentScheduleEntry__c` field name should be used, otherwise, a generic field name is returned.

Default is `false`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

```json
{
    "policyId": "0YT5w000000UPFWGA4",
    "returnSObject": false,
    "getDataCustomClassName": "GetInsurancePolicyPaymentSchedule"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

```json
{
  "output": {
    "policyId": "0YT5w000000UPFWGA4",
    "result": [
      {
        "feeAmount": 10.12,
        "Id": "a5u5w0000005u9ZAAQ",
        "insTransaction": {
          "additionalInfo": null,
          "amount": null,
          "feeAmount": null,
          "Id": "a5t5w000002iF4mAAE",
          "name": null,
          "postDate": null,
          "taxAmount": null,
          "totalAmount": null,
          "transactionDate": null,
          "transactionNumber": null,
          "type": null
        },
        "premiumAmount": 1042.88,
        "scheduleDate": "2020-07-15",
        "taxAmount": 104.29,
        "toDelete": null,
        "totalAmount": 1157.29
      },
      {
        "feeAmount": 1.92,
        "Id": "a5u5w0000005u9aAAA",
        "insTransaction": null,
        "premiumAmount": 192.64,
        "scheduleDate": "2020-07-30",
        "taxAmount": 19.2,
        "toDelete": null,
        "totalAmount": 213.76
      },
      ...
    ],
    "errorCode": "INVOKE-200",
    "error": "OK"
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo