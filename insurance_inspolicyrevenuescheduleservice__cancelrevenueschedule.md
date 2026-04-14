---
title: "InsPolicyRevenueScheduleService:cancelRevenueSchedule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__cancelrevenueschedule.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyRevenueScheduleService:cancelRevenueSchedule

InsPolicyRevenueScheduleService:cancelRevenueSchedule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyRevenueScheduleService:cancelRevenueSchedule

When a policy is canceled, this service adjusts the revenue schedule to calculate revenue until the cancellation date.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsPolicyRevenueScheduleService`

Method: `cancelRevenueSchedule`

[](https://help.salesforce.com/s?language=en_US)

## How it works

1.  This service looks for the policy (asset) ID, the transaction ID, and the effective date for the cancellation of the policy.
    
2.  Uses `modificationType` to query the transaction table `Type` field to get a list of modifications to the policy. If no `modificationType` is specified, the service uses`Changed/Endorsed` by default.
    
3.  Modifies the revenue schedule, removing future unearned revenue from the policy (asset) object.
    
4.  Returns the policy ID in the output JSON.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`assetId`

 | 

Required.

The policy ID of the canceled policy.

 |
| 

`transactionId`

 | 

Required.

The transaction ID that's created when the policy is canceled.

 |
| 

`effectiveDate`

 | 

Required.

The policy cancellation date.

 |
| 

`getDataDRBundleName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the Omnistudio Data Mapper this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| 

`getDataCustomClassName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataDRBundleName`.

 |
| 

`modificationType`

 | 

Required.

The type of modifications made to a policy over its term.

If no value is specified, the services uses `Changed/Endorsed` as the default.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service takes an input JSON.

```
"CancelPolicy": {
	"startDate": "2017-10-31T07:00:00.000Z",
	"endDate": "2018-10-30T07:00:00.000Z",
	"originalPremium": 0,
	"modifyDate": "2018-06-22T07:00:00.000Z",
	"CancelDateValidation": true
},
"PolicyId": "02if200000YfCDEAA3",
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the policy ID in the output JSON.

```
{
    "PolicyId": "02if200000YfCDEAA3"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo