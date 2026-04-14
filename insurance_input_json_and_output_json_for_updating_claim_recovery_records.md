---
title: "Input JSON and Output JSON for Updating Claim Recovery Records"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_updating_claim_recovery_records.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Input JSON and Output JSON for Updating Claim Recovery Records

Input JSON and Output JSON for Updating Claim Recovery Records[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Input JSON and Output JSON for Updating Claim Recovery Records

Use `InsClaimService:createUpdateClaimRecoveries` to update claim recovery records when claims agents either accept recovery amounts, or accept recovery amounts and seek additional recovery.

## Input JSON for Updating Claim Recovery Records

In this example of input JSON, the insurance carrier accepts a $6,000 recovery amount and continues to pursue more. The status is `Accepted with Additional Pursuit`.

```json
{
  "claimRecoveries": [
   {
     "status": "Accepted with Additional Pursuit",
     "actualRecoveryAmount" : 6000,
     "id": "0t6xx000000004r"
   }
 ]
}
```

In this example, the insurance carrier accepts a $6,000 recovery amount without pursuing more. The status is `Accepted Recovery`.

```json
{
  "claimRecoveries": [
   {
     "status": "Accepted Recovery",
     "actualRecoveryAmount" : 6000,
     "id": "0t6xx000000004r"
   }
 ]
}
```

## Output JSON for Updating Claim Recovery Records

This example of output JSON shows an actual recovery amount and the `Accepted with Additional Pursuit` status.

```json
{
 "totalProcessedClaimRecoveries": 1,
 "totalClaimRecoveries": 1,
 "errors": [],
 "claimRecoveries": [
   {
     "additionalFields": {},
     "currencyIsoCode": "USD",
     "recoveredOnDate": "2022-07-18",
     "status": "Accepted with Additional Pursuit",
     "actualRecoveryAmount": "6000.0",
     "estimatedRecoveryAmount": "10000.0",
     "recoveryFromAccountId": "001RO000003sAqaYAE",
     "recoveryType": "Salvage",
     "claimCoverageId": "0kPxx0000000001",
     "claimId": "0Zkxx0000000001",
     "name": "Recovery for BMW & Truck Collision1",
     "id": "0t6xx000000004r"
   }
 ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo