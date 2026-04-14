---
title: "InsClaimRecoveryService:getRecoveries"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__getrecoveries.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimRecoveryService:getRecoveries

InsClaimRecoveryService:getRecoveries[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimRecoveryService:getRecoveries

Use this service to get a list of claim recoveries (**InsuranceClaimRecovery\_\_c**) based on a specified claim Id or claim number.

Class: `InsClaimRecoveryService`

Method: `getRecoveries`

Works with: Vlocity object model

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  The user provides **claimId**, **claimNumber**, or both as inputs.
    
2.  The service uses the inputs to get a list of claim recoveries associated with that claim.
    
3.  The service returns a list of claim recoveries.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**claimId**

 | 

Claim Id of claim recoveries to obtain.

 |
| 

**claimNumber**

 | 

Claim number (**InsuranceClaim\_\_c.Name**) of claim recoveries to obtain.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

```
{ 
   "Options": {
      "claimId": "a4X3j0000001iTcEAI"
    }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

```
{  
  "claimRecoveries": [
    {
      "Name": "Recovery 1",
      "Amount__c": 500,
      "AssignmentDate__c": "2020-04-01",
      "ClaimId__c": "a4X3j0000001iTcEAI",
      "CollectionsAssignmentDate__c": "2020-04-01",
      "Status__c": "Pending",
      "StatusAsOfDate__c": "2020-04-24",
      "Type__c": "Salvage",
      "Id": "a4V3j000000y83BEAQ"
    },
    {
      "Name": "Recovery2",
      "Amount__c": 300,
      "AssignmentDate__c": "2020-04-01",
      "ClaimId__c": "a4X3j0000001iTcEAI",
      "CollectionsAssignmentDate__c": "2020-04-01",
      "Status__c": "Pending",
      "StatusAsOfDate__c": "2020-04-24",
      "Type__c": "Salvage",
      "Id": "a4V3j000000y83GEAQ"
    },
    {
      "Name": "Recovery3",
      "Amount__c": 1000,
      "AssignmentDate__c": "2020-04-01",
      "ClaimId__c": "a4X3j0000001iTcEAI",
      "CollectionsAssignmentDate__c": "2020-04-01",
      "Status__c": "Pending",
      "StatusAsOfDate__c": "2020-04-24",
      "Type__c": "Salvage",
      "Id": "a4V3j000000y83HEAQ"
    }
  ],
  "errorCode": "INVOKE-200",
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo