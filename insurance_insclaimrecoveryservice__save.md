---
title: "InsClaimRecoveryService:save"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__save.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimRecoveryService:save

InsClaimRecoveryService:save[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimRecoveryService:save

Use this service to accept an input of a list of information, which is transformed to create and update records for the InsuranceClaimRecovery\_\_c, an object that represents the recovery of funds for a claim.

Class: **InsClaimRecoveryService**

Method: **save**

Works with: Vlocity object model

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  Takes the input JSON for a list of fields and values and saves this information in a Claim Recovery record.
    
    The option JSON must contain **inputKey**, which is the name of the input JSON that contains the claim recovery information.
    
2.  Passes the inputs.
    
3.  Passes these inputs and options JSON to the service and gets the service's output.
    
4.  If no input jSON or no **inputKey** element in the output JSON, the service ends unsuccessfully.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**inputKey**

 | 

The node/element name of the input JSON that you're going to pass

 |
| 

**allOrNone**

 | 

Boolean value that determines if saving will proceed even if there are records in the list that has errors.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

```
{ 
   "claimRecovery": [
    {
      "status": "Pending",
      "type": "Salvage",
      "collectionsAssignmentDate": "2020-04-02",
      "assignmentDate": "2020-04-01",
      "amount": 300,
      "claimIdOrNumber": "a4X3j0000001iTcEAI",
      "Name": "Recovery1"
    },
    {
      "status": "Pending",
      "type": "Salvage",
      "collectionsAssignmentDate": "2020-04-16",
      "assignmentDate": "2020-04-01",
      "amount": 1000,
      "claimIdOrNumber": "a4X3j0000001iTcEAI",
      "Name": "Recovery2"
    }
  ]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

```
{  
  "numberOfFailedSave": 0,
  "failedSavingErrors": [],
  "processedClaimRecoveries": [
    "a4V3j000000y83GEAQ",
    "a4V3j000000y83HEAQ"
  ],
  "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo