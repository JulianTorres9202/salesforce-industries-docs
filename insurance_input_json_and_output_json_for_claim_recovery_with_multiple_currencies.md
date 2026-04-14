---
title: "Input JSON and Output JSON for Claim Recovery with Multiple Currencies"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_claim_recovery_with_multiple_currencies.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Input JSON and Output JSON for Claim Recovery with Multiple Currencies

Input JSON and Output JSON for Claim Recovery with Multiple Currencies[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Input JSON and Output JSON for Claim Recovery with Multiple Currencies

Use `InsClaimService:createUpdateClaimRecoveries` to track claim recovery in organizations that use multiple currencies.

## Input JSON for Claim Recovery with Multiple Currencies

This example of input JSON creates a Claim Recovery record that includes `currencyIsoCode`. In cases where agents seek additional recovery amounts, the new Claim Recovery record created for the additional pursuit uses the currency of the parent Claim Recovery record by default.

```json
{
  "claimRecoveries": [
    {
      "status": "Accepted Recovery",
      "recoveryType": "Salvage",
      "estimatedRecoveryAmount": 1000,
      "actualRecoveryAmount": 900,
      "recoveryFromAccountId": "001RO000003sAqaYAE",
      "claimCoverageId": "0kPRO00000001mG",
      "claimId": "0ZkRO00000005YJ",
      "name": "Recovery1",
      "currencyIsoCode": "USD"
    }
  ]
}
```

## Output JSON for Claim Recovery with Multiple Currencies

This example of output JSON creates a Claim Recovery record that includes `currencyIsoCode`.

```json
{
  "totalProcessedClaimRecoveries": 1,
  "totalClaimRecoveries": 1,
  "errors": [

  ],
  "claimRecoveries": [
    {
      "additionalFields": {

      },
      "currencyIsoCode": "USD",
      "recoveredOnDate": "2022-07-18",
      "status": "Accepted Recovery",
      "actualRecoveryAmount": "900.0",
      "estimatedRecoveryAmount": "1000.0",
      "recoveryType": "Salvage",
      "recoveryFromAccountId": "001RO000003sAqaYAE",
      "claimCoverageId": "0kPRO00000001mG",
      "claimId": "0ZkRO00000005YJ",
      "name": "Recovery1",
      "id": "0t6xx0000000001AAA"
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo