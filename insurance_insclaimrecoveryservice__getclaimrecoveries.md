---
title: "InsClaimService:getClaimRecoveries"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__getclaimrecoveries.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimService:getClaimRecoveries

InsClaimService:getClaimRecoveries[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimService:getClaimRecoveries

Use this service to get a list of claim recoveries for a claim.

**Class**:`InsClaimService`

**Method**:`getClaimRecoveries`

**Works with**: Salesforce FSC ClaimRecovery object

## How It Works

The service:

1.  Takes a `claimId` as input.
    
2.  Returns a count of records processed (`totalProcessedClaimRecoveries`), a count of records returned (`totalClaimRecoveries`), errors, and a node with claim recovery fields and values.
    

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`inputKey`

 | 

Required.

The name of the node to pass as input JSON, for example `recoveryOptions`.

 |
| 

`claimNumber`

 | 

Required.

The claim associated with the claim recoveries.

 |

## Input JSON

Here's a sample of input JSON. In this example, the service gets a list of claim recoveries for a claim with an ID of `0Zkxx0000000001CAA`.

```json
{
 "recoveryOptions": [
   {
     "claimId": "0Zkxx0000000001CAA"
   }
 ]
}
```

## Output JSON

Output shows all the Claim Recovery records created for a particular claim. Output includes either a single record or multiple records based on the number of Claim Recovery records per claim.

Here's a sample of output JSON for a claim with one Claim Recovery record.

```json
{
 "totalProcessedClaimRecoveries": 1,
 "totalClaimRecoveries": 1,
 "errors": [],
 "claimRecoveries": [
   {
     "additionalFields": {},
     "recoveredOnDate": "2022-07-18",
     "status": "Accepted Recovery",
     "actualRecoveryAmount": "3500.0",
     "estimatedRecoveryAmount": "4500.0",
     "recoveryFromAccountId": "001xx000003GZwVAAW",
     "recoveryType": "Salvage",
     "claimCoverageId": "0kPxx0000000001EAA",
     "claimId": "0Zkxx0000000001CAA",
     "name": "Claim Recovery One",
     "id": "0t6xx0000000001AAA"
   }
 ],
 "errorCode": "INVOKE-200",
 "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo