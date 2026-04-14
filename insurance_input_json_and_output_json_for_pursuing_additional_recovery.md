---
title: "Input JSON and Output JSON for Pursuing Additional Recovery"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_pursuing_additional_recovery.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Input JSON and Output JSON for Pursuing Additional Recovery

Input JSON and Output JSON for Pursuing Additional Recovery[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Input JSON and Output JSON for Pursuing Additional Recovery

Use `InsClaimService:createUpdateClaimRecoveries` to update and add claim recovery records when claims agents pursue additional recovery.

For the pursuit of an additional recovery amount, the service:

1.  Updates the original Claim Recovery record.
    
2.  Creates a new Claim Recovery record using inputs provided in `additionalFields`.
    

The `claimId` and `claimCoverageId` values must match those used in the original Claim Recovery record, and the service requires `actualRecoveryAmount` from the original Claim Recovery record.

## Input JSON for Pursuing Additional Recovery

In this example of input JSON:

```json
{
  "claimRecoveries": [
  {
     "actualRecoveryAmount" : 2000
     "recoveryFromAccountId" : "001RO000003sAqaYAE",
     "claimCoverageId": "0kPRO00000001mG",
     "claimId": "0ZkRO00000005YJ",
     "recoveredOnDate" : "2022-03-16",
     "id": "0t6RO00000004CN",
     "status" : "Accepted with Additional Pursuit"
     "additionalFields": {
       "repursueAmount" : 900,
       "repurseClaimRecoveryName" : "Repursued BMW Crash Claim recovery",
       "repursueStatus" : "Additional Recovery Pursued"
     }
   }
 ]
}
```

-   Updates are for the original Claim Recovery record with the `recoveryId` `0t6RO00000004CN` (`"id": "0t6RO00000004CN"`).
    
-   The original record's status is set to `Accepted with Additional Pursuit`.
    
-   The new record's status is set to `Additional Recovery Pursued`.
    

## Output JSON for Pursuing Additional Recovery

Output JSON for the pursuit of an additional recovery amount includes two records: the updated original Claim Recovery record and the new Claim Recovery record for the additional pursuit. The new record uses the same `claimId` and `claimCoverageId` as the original record.

```json
{
  "totalProcessedClaimRecoveries": 2,
  "totalClaimRecoveries": 2,
  "errors": [

  ],
  "claimRecoveries": [
    {
      "additionalFields": {

      },
      "recoveredOnDate": "2022-07-18",
      "status": "Accepted with Additional Pursuit",
      "actualRecoveryAmount": "2000.0",
      "estimatedRecoveryAmount": "4500.0",
      "recoveryFromAccountId": "001xx000003GZwVAAW",
      "recoveryType": "Salvage",
      "claimCoverageId": "0kPxx0000000001EAA",
      "claimId": "0Zkxx0000000001CAA",
      "name": "Claim Recovery One",
      "id": "0t6xx0000000001AAA"
    },
    {
      "additionalFields": {

      },
      "claimCoverageId": "0kPxx0000000001",
      "claimId": "0Zkxx0000000001",
      "name": "Repursued BMW Crash Claim recovery",
      "estimatedRecoveryAmount": "4500.0",
      "status": "Additional recovery pursued",
      "id": "0t6xx000000001d"
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo