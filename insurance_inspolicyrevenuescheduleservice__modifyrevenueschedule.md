---
title: "InsPolicyRevenueScheduleService:modifyRevenueSchedule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyrevenuescheduleservice__modifyrevenueschedule.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyRevenueScheduleService:modifyRevenueSchedule

InsPolicyRevenueScheduleService:modifyRevenueSchedule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyRevenueScheduleService:modifyRevenueSchedule

This service takes in the modifications done to the policy. Based on the changes to total policy premium and the modification date, it recalculates the revenue schedule to adjust the unpaid monthly premiums (unearned revenue).

This service supports the use of the Salesforce Financial Services Cloud.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsPolicyRevenueScheduleService`

Method: `modifyRevenueSchedule`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Looks for the policy (asset) ID of the policy being modified, the transaction ID created when the policy is modified, and the effective date of the policy modification.
    
2.  Calculates the modified revenue schedule, including the earned and unearned revenue amounts for each month from the modification effective date through the expiration date of the policy.
    
3.  Calculates the modified revenue schedule, including the earned and unearned revenue amounts for each month from the modification effective date through the expiration date of the policy.
    

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

The asset (policy) Id of the new policy version.

 |
| 

`transactionId`

 | 

Required.

The Id of the Changed/Endorsed transaction on the original policy.

 |
| 

`effectiveDate`

 | 

Optional.

The date the modification goes into effect.

Defaults to today's date if left blank.

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

`postDate`

 | 

Optional.

The date you posted the modification.

Defaults to today's date if left blank.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't use the input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service does not return any useful content in the output JSON.

The service updates the database with the modified earned and unearned revenue schedule entries.

Did this article solve your issue?

Let us know so we can improve!

YesNo