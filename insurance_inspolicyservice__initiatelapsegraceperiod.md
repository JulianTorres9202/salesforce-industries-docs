---
title: "InsPolicyService:initiateLapseGracePeriod"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__initiatelapsegraceperiod.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:initiateLapseGracePeriod

InsPolicyService:initiateLapseGracePeriod[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:initiateLapseGracePeriod

This service initiates a grace period on a policy, lapses a policy, or does nothing to a policy, depending on factors of the policy.

This service works with the Vlocity Policy (Asset) object, not the Salesforce FSC InsurancePolicy object.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `inititateLapseGracePeriod`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `assetId` and retrieves the policy.
    
2.  Retrieves the `Status`, `GracePeriodStartDate__c`, `GracePeriodEndDate__c`, and `ExpirationDate__c` values from the policy.
    
3.  If Status = `Active` and the `GracePeriodStartDate__c` is greater than or equal to today:
    
    1.  Updates the Status to `Pending Lapse`.
        
    2.  Creates a new transaction on the policy of type `Initiate Grace Period` with effective date = `GracePeriodStartDate__c`.
        
4.  If the Status = `Pending Lapse` and the `GracePeriodEndDate__c` is greater than or equal to today:
    
    1.  Updates the Status to `Lapsed`.
        
    2.  Sets the `OriginalExpirationDate__c` of the policy to `ExpirationDate__c`.
        
    3.  Sets the `ExpirationDate__c` of the policy to today.
        
    4.  If the policy has a Billing Account the `BillStatus__c` on the Billing Account is set to `Terminated`. Otherwise, the `BillStatus__c` on the policy is set to `Terminated`.
        
5.  Returns the Id of the created transaction in the `transactionId` field.
    

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

%theIdYouAreLookingFor%

The Id of the policy to initiate grace period or lapse.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not require any input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Output JSON includes the following key and its value:

-   `transactionId`: Id of transaction record created
    

```
{
    "transactionId": "a3g5A000000YRPpQAO"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo