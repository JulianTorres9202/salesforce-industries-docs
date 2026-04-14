---
title: "InsPolicyRevenueScheduleService:createRevenueSchedule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__createrevenueschedule.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyRevenueScheduleService:createRevenueSchedule

InsPolicyRevenueScheduleService:createRevenueSchedule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyRevenueScheduleService:createRevenueSchedule

This service creates a monthly revenue schedule for a policy, starting on the effective date of the policy and ending on the expiration date of the policy term.

This service supports Salesforce Financial Services Cloud.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsPolicyRevenueScheduleService`

Method: `createRevenueSchedule`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service looks for the policy Id (`assetId`) and the `transactionId` that recorded the sale of the policy.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    If you're using this service on an org that uses Salesforce Financial Services Cloud, you must use `getDataDRBundleNames` or `getDataCustomClassName` as input in addition to these options.
    
2.  Creates a list of revenue schedule entries for the policy. Each entry contains the following information:
    
    [](https://help.salesforce.com/s?language=en_US)
    
    -   Date: The end of each month, starting with the effective date of the policy and ending the last month of the policy term.
        
    -   Total Earned Revenue: Total revenue you have earned for this policy by this date.
        
    -   Total Unearned Revenue: Revenue you have not yet earned for this policy by this date.
        
    -   Period Earned Revenue: The revenue you earn for this policy during this month.
        
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    If you're using this service on an org that uses Salesforce Financial Services Cloud, you must use `postDataDRBundleName` or `postDataCustomClassName` to post the revenue schedule to the FSC.
    
3.  Returns the total policy revenue to be earned, if the policy is not canceled or modified, in the output JSON.
    

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

The ID of this policy.

 |
| 

`getDataCustomClassName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataDRBundleName`.

 |
| 

`getDataDRBundleName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the Omnistudio Data Mapper this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| `postDataCustomClassName` | 

The name of the custom class this service uses to save the new policy version.

If you're using Salesforce FSC, you must specify either this option or `postDataDRBundleName`.

 |
| `postDataDRBundleName` | 

The name of the Data Mapper this service uses to save the new policy version.

If you're using Salesforce FSC, you must specify either this option or `postDataCustomClassName`.

 |
| 

`transactionId`

 | 

The ID of the transaction associated with the creation of the policy.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the total revenue you will earn for this policy (if it isn't canceled or modified).

```
{
    "totalEarned": 533.8
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo