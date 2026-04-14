---
title: "InsClaimCoverageService:createUpdateCoverage"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimcoverageservice_createupdatecoverage.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimCoverageService:createUpdateCoverage

InsClaimCoverageService:createUpdateCoverage[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimCoverageService:createUpdateCoverage

Use this service to create a claim coverage or update an existing claim coverage.

`Class`: InsClaimCoverageService

`Method`: createUpdateCoverage

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  The following inputs, which can be passed as remote options, must be passed to the service for creating a claim coverage:
    
    Important
    
    The user can’t create a claim coverage when an existing claim coverage has equal values for the following fields: claimId, claimantId, involvedId, insuredId, and assetCoverageId.
    
    -   **claimId**
        
        [](https://help.salesforce.com/s?language=en_US)Note
        
        Depending on the **claimID** input, the service creates either a Vlocity Claim Coverage (**ClaimCoverage\_\_c**) or a Salesforce Claim Coverage (**ClaimCoverage**). If the **claimID** is an ID of the **InsuranceClaim\_\_c** object, the Claim Coverage is Vlocity Claim Coverage, else the service creates a Salesforce Claim Coverage.
        
    -   **claimCoverageId**
        
    -   **claimantId**
        
    -   **involvedId**
        
    -   **insuredId**
        
    -   **assetCoverageId**
        
    -   **reserveAmount**
        
    -   **reserveProcessingMode**
        
    
    Note
    
    When updating an existing claim coverage, the only required inputs are **claimCoverageId** and **reserveAmount**. You can leave the other fields blank.
    
2.  The service processes this information and creates a coverage if the **claimCoverageId** is blank. Otherwise, the service updates the existing claim coverage with the Id equal to **claimCoverageId**.
    
    The claim coverage reserve amount won’t be set if you set **reserveProcessingMode** to **ReserveWorksheet**.
    
    If you want to require the claim coverage reserve amount, you can set **reserveProcessingMode** as **CoverageReserve**.
    

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

Required for new claim coverages.

The Id of the claim on which you want to create the claim coverage.

[](https://help.salesforce.com/s?language=en_US)Note

Depending on the **claimID** input, the service creates either a Vlocity Claim Coverage (**ClaimCoverage\_\_c**) or a Salesforce Claim Coverage (**ClaimCoverage**). If the **claimID** is an ID of the **InsuranceClaim\_\_c** object, the Claim Coverage is Vlocity Claim Coverage, else the service creates a Salesforce Claim Coverage.







 |
| 

**claimCoverageId**

 | 

Required for the update of an existing claim coverage.

The Id of existing claim coverage. If blank, the service creates a claim coverage. Otherwise, the service updates the existing claim coverage.

For Vlocity Data Model, the claimCoverageId is **ClaimCoverage\_\_c.Id**.

For Salesforce Data Model, the claimCoverage Id is **ClaimCoverage.Id**.

 |
| 

**claimantId**

 | 

Required for new claim coverages.

The Id of an existing claimant. The claimant must be related to the claim indicated in the claimId.

For Vlocity Data Model, the claimantId is **InsuranceClaimPartyRelationship\_\_c.Id**.

For Salesforce Data Model, the claimantId is **ClaimParticipant.Id**.

 |
| 

**involvedId**

 | 

Required for new claim coverages.

The Id of an existing involved property or involved person. For Salesforce Data Model, it’s the Id of an existing claim item related to the claim.

For Vlocity Data Model, the involvedId is **InsuranceClaimInvolvedProperty\_\_c.Id**/**InsuranceClaimInvolvedInjury\_\_c.Id**.

For Salesforce Data Model, the involvedId is **ClaimItem.Id**.

 |
| 

**insuredId**

 | 

Required for new claim coverages.

The Id of an existing policyholder/insured item held product relationship. For Salesforce Data Model, it’s the Id of an existing Policy Asset.

For Vlocity Data Model, the insuredId is **AssetInsuredItem\_\_c.Id** or **AssetPartyRelationship\_\_c.Id**.

For Salesforce Data Model, the insuredId is **InsurancePolicyAsset.Id**.

 |
| 

**assetCoverageId**

 | 

Required for new claim coverages.

The Id of a policy coverage related to the claim's policy.

For Vlocity Data Model, the assetCoverageId is **AssetCoverage\_\_c.Id**.

For Salesforce Data Model, the assetCoverageId is **InsurancePolicyCoverage.Id**.

 |
| 

**reserveAmount**

 | 

Required for new claim coverages.

The reserve amount.

 |
| 

**reserveProcessingMode**

 | 

Required for new claim coverages.

The reserve processing mode of the claim coverage. The values can be either **CoverageReserve** or **ReserveWorksheet**.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of input JSON:

```
{
    "claimId": <Id>,
    "claimCoverageId": <Id>,
    "claimantId": <Id>,
    "involvedId": <Id>,
    "insuredId": <Id>,
    "assetCoverageId": <Id>,
    "reserveAmount": <Decimal>,
    "reserveProcessingMode": <String>
}
```

Here's the sample of input JSON.

```
{
    "claimId": "a4X3j0000001iTcEAI",
    "claimCoverageId": null,
    "claimantId": "a4U3j000000LjtQEAS",
    "involvedId": "a4S3j000000QXjTEAW",
    "insuredId": "a3v3j000000d5UsAAI",
    "assetCoverageId": "a3u3j00000Pvx5hAAB",
    "reserveAmount": 300,
    "reserveProcessingMode": "CoverageReserve"
}  
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of output JSON:

```
{
      "claimCoverage": [
        {
          "reserveProcessingMode": <String>,
          "lossReserveAmount": <Decimal>,
          "name": <String>,
          "involvedName": <String>,
          "claimItemId": <Id>,
          "description": <String>,
          "claimParticipantName": <String>,
          "claimParticipantId": <Id>,
          "claimId": <Id>,
          "status": <String>,
          "insurancePolicyAssetId": <Id>,
          "insurancePolicyCoverageName": <String>,
          "insurancePolicyCoverageId": <Id>,
          "createdDate": <Date>
        }
      ],
      "claimCoverageId": <Id>,
      "errorCode": <String>,
      "error": <String>
}
```

Here's the sample of output JSON.

```
{
      "claimCoverage": [
        {
          "reserveProcessingMode": "CoverageReserve",
          "lossReserveAmount": 300,
          "name": "Jewelry",
          "involvedName": null,
          "claimItemId": "a4S3j000000QXjTEAW",
          "description": null,
          "claimParticipantName": null,
          "claimParticipantId": "a4U3j000000LjtQEAS",
          "claimId": "a4X3j0000001iTcEAI",
          "status": null,
          "insurancePolicyAssetId": "a3v3j000000d5UsAAI",
          "insurancePolicyCoverageName": null,
          "insurancePolicyCoverageId": "a3u3j00000Pvx5hAAB",
          "createdDate": null
        }
      ],
      "claimCoverageId": "a5G3j000000YEhDEAW",
      "errorCode": "INVOKE-200",
      "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo