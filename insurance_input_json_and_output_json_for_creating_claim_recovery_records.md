---
title: "Input JSON and Output JSON for Creating Claim Recovery Records"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_creating_claim_recovery_records.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Input JSON and Output JSON for Creating Claim Recovery Records

Input JSON and Output JSON for Creating Claim Recovery Records[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Input JSON and Output JSON for Creating Claim Recovery Records

Use `InsClaimService:createUpdateClaimRecoveries` to create claim recovery records when claims agents pursue recovery amounts.

## Input JSON for Creating Claim Recovery Records

In this example of input JSON, a claims agent pursues a $10,000 recovery amount.

```json
{
  "claimRecoveries": [
   {
     "status": "Pursued",
     "recoveryType": "Salvage",
     "estimatedRecoveryAmount": 10000,
     "recoveryFromAccountId" : "001RO000003sAqaYAE",
     "claimCoverageId": "0kPxx0000000001",
     "claimId": "0Zkxx0000000001",
     "name": "Recovery for BMW & Truck Collision1"
   }
 ]
}
```

## Output JSON for Creating Claim Recovery Records

In this example of output JSON, the service creates a Claim Recovery record with an ID of `t6xx000000004r`.

```json
{
 "totalProcessedClaimRecoveries": 1,
 "totalClaimRecoveries": 1,
 "errors": [],
 "claimRecoveries": [
   {
     "additionalFields": {},
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