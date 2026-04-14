---
title: "InsClaimService:createUpdateClaimRecoveries"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimrecoveryservice__createupdateclaimrecoveries.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimService:createUpdateClaimRecoveries

InsClaimService:createUpdateClaimRecoveries[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimService:createUpdateClaimRecoveries

Use this service to create or update records that represent a recovery of funds on an insurance claim.

Class: `InsClaimService`

Method: `createUpdateClaimRecoveries`

Works with: Salesforce FSC ClaimRecovery object

## How It Works

The service:

1.  Gets a pre-transformed JSON called by the `inputKey`.
    
2.  Creates a Claim Recovery object if a `claimId` is passed in, or updates a Claim Recovery object if a `recoveryId` is passed in.
    
3.  Returns a count of records processed (`totalProcessedClaimRecoveries`), a count of records created or updated (`totalClaimRecoveries`), errors, and a node with claim recovery fields and values.
    

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

Required

The name of the node to pass as input JSON, for example `claimRecoveries`.

 |
| 

`accountId`

 | 

Optional.

The account related to the claim.

 |
| 

`claimCoverageId`

 | 

Optional.

The claim coverage associated with the claim recovery. Must be a valid value for the given `claimId`.

 |
| 

`claimId`

 | 

Required to create a Claim Recovery record, optional to update a Claim Recovery record.

The claim associated with the claim recovery. Must match the `claimId` related to the given `recoveryId`, if `recoveryId` is included.

 |
| 

`currencyIsoCode`

 | 

Optional.

If your organization uses multiple currencies, the currency of the claim. recoveryId: Required to update a Claim Recovery record. The ID of the Claim Recovery record.

 |
| 

`estimatedRecoveryAmount`

 | 

Optional.

The estimated amount the insurance carrier identified to pursue for the claim recovery.

 |
| 

`name`

 | 

Required.

The name of the Claim Recovery record.

 |
| 

`recoveredOnDate`

 | 

Optional.

The timestamp the amount was recovered. For multicurrency scenarios, the recovery date is used to retrieve currency conversion rates.

 |
| 

`recoveryFromAccountId`

 | 

Optional.

The account that the claim is recovered from.

 |
| 

`recoveryId`

 | 

Required to update a Claim Recovery record.

The Claim Recovery record.

 |
| 

`recoveryType`

 | 

Optional.

Type of claim recovery. Possible values include: Salvage, Subrogation.

 |
| 

`status`

 | 

Optional.

Status of the claim recovery. Possible values include: Accepted Recovery, Accepted with Additional Pursuit, Additional Recovery Pursued, Disputed Recovery, Estimated, Partially Recovered, Pursued, Recovery Canceled, Recovery Written Off, Referred to Other Department.

 |
| 

`additionalFields`

 | 

Required when pursuing additional recovery.

The key-value pairs for new Claim Recovery records created in update scenarios.

 |

## Input JSON and Output JSON

Review examples of input JSON and output JSON for `InsClaimService: createUpdateClaimRecoveries`.

-   **[Input JSON and Output JSON for Creating Claim Recovery Records](https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_creating_claim_recovery_records.htm&language=en_US&type=5)**  
    Use `InsClaimService:createUpdateClaimRecoveries` to create claim recovery records when claims agents pursue recovery amounts.
-   **[Input JSON and Output JSON for Updating Claim Recovery Records](https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_updating_claim_recovery_records.htm&language=en_US&type=5)**  
    Use `InsClaimService:createUpdateClaimRecoveries` to update claim recovery records when claims agents either accept recovery amounts, or accept recovery amounts and seek additional recovery.
-   **[Input JSON and Output JSON for Claim Recovery with Multiple Currencies](https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_claim_recovery_with_multiple_currencies.htm&language=en_US&type=5)**  
    Use `InsClaimService:createUpdateClaimRecoveries` to track claim recovery in organizations that use multiple currencies.
-   **[Input JSON and Output JSON for Pursuing Additional Recovery](https://help.salesforce.com/s/articleView?id=ind.insurance_input_json_and_output_json_for_pursuing_additional_recovery.htm&language=en_US&type=5)**  
    Use `InsClaimService:createUpdateClaimRecoveries` to update and add claim recovery records when claims agents pursue additional recovery.

Did this article solve your issue?

Let us know so we can improve!

YesNo