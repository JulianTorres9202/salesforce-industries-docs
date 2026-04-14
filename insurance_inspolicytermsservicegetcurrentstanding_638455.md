---
title: "InsPolicyTermsService:getCurrentStanding"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservicegetcurrentstanding_638455.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyTermsService:getCurrentStanding

InsPolicyTermsService:getCurrentStanding[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyTermsService:getCurrentStanding

Use this service to get a list of amounts that represent the current standing of the policy terms associated with a policy or a claim.

[](https://help.salesforce.com/s?language=en_US)

`Class`: `InsPolicyTermsService`

[](https://help.salesforce.com/s?language=en_US)

`Method`: `getCurrentStanding`

[](https://help.salesforce.com/s?language=en_US)

Note

This service populates the Policy Term Current Standings for both the Policy and Claim pages. To configure the policy terms standings on the insurance claim record page, use the Vlocity Policy Terms Standing LWC. To configure the policy terms standings with a capability to filter the coverage details based on the `insuredId` on the insurance policy record page, use the Policy Terms Standing - Insurance Policy View component.

[](https://help.salesforce.com/s?language=en_US)

Important

With the Summer '21 release, the same service supports Salesforce FSC Claim Data Models to display the consumed power attributes.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes an object Id, which can be any of these values: policy Id, claim Id, policyCoverageId, policyParticipantId, or policyAssetId.
    
2.  The service takes an optional `viewOption` node.
    
    1.  If the objectId is policyId, the service takes either of these two options:
        
        1.  `showAllPolicyCoverage`
            
        2.  `showPolicyLevelTermsOnly`
            
    2.  If the objectId is claimId, the service takes either of these two options:
        
        1.  `showAllPolicyCoverages`
            
        2.  `showOpenClaimPolicyCoverages`
            
3.  Returns a list of policy terms associated with the objectId. The name created for this node depends on the attribute class and attribute scope of the given policy term.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`objectId`

 | 

Required.

The ID to fetch the current standing of the policy terms.

Possible values:

-   `policyId`
    
-   `claimId`
    
-   `policyCoverageId`
    
-   `policyParticipantId`
    
-   `policyAssetId`.
    

 |
| 

`viewOption`

 | 

Optional.

Scenario 1: When objectId is `claimId`, the possible values are:

-   `showAllPolicyCoverages`
    
    Show all policy term current standings regardless of whether the policy has open claim coverages.​​
    
-   `showOpenClaimPolicyCoverages`
    
    Show policy term current standings with open claim coverages only. In Claim view, show all policy or claim scope policy terms, regardless of whether there's an open claim coverage. The default option when the objectId is `claimId`.
    

 |
| 

Scenario 2: When objectId is `policyId`, the possible values are:

-   `showAllPolicyCoverages`
    
    Show all policy terms for the root insurance policy and all the policy coverages. The default option when the objectId is `claimId`.
    
-   `showPolicyLevelTermsOnly`
    
    Show all policy term current standings with Policy scope and Policy Coverage scope without any Policy Participant and Policy Asset associated with it.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the sample input JSON:

```
{ 
   "objectId": <Id>
}
```

Here's a sample input JSON:

```
{ 
   "objectId":"a2b5w000006SBY9AAO"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of the sample output JSON:

```
{ 
   "currentStanding": [
    {
      <String:Policy Term Name>: {
        "predictedRemainingValue": <Decimal>,
        "pendingValue": <Decimal>,
        "usedValue": <Decimal>,
        "remainingValue": <Decimal>,
        "initialValue": <Decimal>,
        "dataType": <Text>,
        "insurancePolicyCoverageName": <Text>,
        "insuredItemId": <Id>,
        "insuredPartyId": <Id>,
        "assetCoverageId": <Id>,
        "assetId": <Id>,
        "attributeScope": <Text>,
        "attributeClass": <Text>,
        "assetTermName": <Text>,
        "assetTermId": <Id>,
        "claimId": <Id>,
        "claimCoverageIds": [<List of Ids>]
      }
    }
  ]
}
```

How the policy term name is constructed depends on how the power attribute is set up. Here are some examples of different configurations that create different policy term names.

Policy Term Name: General Contents Policy Limit

Attribute Class: Limit - Currency

Attribute Scope: Policy Output

Name: General Contents Policy Limit

```
{ 
   "currentStanding": [
    {
        "General Contents Policy Limit": {
            "predictedRemainingValue": 500,
            "pendingValue": 0,
            "usedValue": 0,
            "remainingValue": 500,
            "initialValue": 500,
            "dataType": "currency",
            "insurancePolicyCoverageName": "Lab",
            "insuredPartyId": null,
            "insuredItemId": null,
            "assetCoverageId": "a3u3j00000HyNvYAAV",
            "assetId": "02i3j00000KhumpAAB",
            "attributeScope": "Policy",
            "attributeClass": "Limit",
            "assetTermName": "General Contents Policy Limit",
            "assetTermId": "a5N3j000000XnVtEAK"
        }
    }
  ]
}
```

Policy Term Name: General Contents Policy Coverage Limit

Attribute Class: Limit - Currency

Attribute Scope: Policy Coverage Output

Name: General Contents Policy Coverage Limit - Sample Insured

```
{ 
   "currentStanding": [
    {
        "General Contents Policy Coverage Limit - Sample Insured": {
            "predictedRemainingValue": 500,
            "pendingValue": 0,
            "usedValue": 0,
            "remainingValue": 500,
            "initialValue": 500,
            "dataType": "currency",
            "insurancePolicyCoverageName": "Outpatient",
            "insuredPartyId": "0ao8c000000PnSqAAK",
            "insuredItemId": null,
            "assetCoverageId": "a3u3j00000HyNvYAAV",
            "assetId": "02i3j00000KhumpAAB",
            "attributeScope": "Policy Coverage",
            "attributeClass": "Limit",
            "assetTermName": "General Contents Policy Coverage Limit",
            "assetTermId": "a5N3j000000XnVtEAK"
        }
    }
  ]
}
```

Policy Term Name: General Contents Claim Limit

Attribute Class: Limit - Currency

Attribute Scope: Claim Output Name: General Contents Claim Limit

```
{ 
   "currentStanding": [
    {
        "General Contents Claim Limit": {
            "predictedRemainingValue": 500,
            "pendingValue": 0,
            "usedValue": 0,
            "remainingValue": 500,
            "initialValue": 500,
            "dataType": "currency",
            "insurancePolicyCoverageName": "Lab",
            "insuredPartyId": null,
            "insuredItemId": null,
            "assetCoverageId": "a3u3j00000HyNvYAAV",
            "assetId": "02i3j00000KhumpAAB",
            "attributeScope": "Claim",
            "attributeClass": "Limit",
            "assetTermName": "General Contents Claim Limit",
            "assetTermId": "a5N3j000000XnVtEAK",
            "claimId": "a4X3j0000001gUPEAY",
            "claimCoverageIds": ["a5G3j000000YGYwEAO"]
        }
    }
  ]
}
```

Policy Term Name: General Contents Claim Coverage Limit

Attribute Class: Limit - Currency

Attribute Scope: Claim Coverage Output

Name: General Contents Claim Coverage Limit - Test Party (Joan Smith)

```
{ 
   "currentStanding": [
    {
      "General Contents Claim Coverage Limit - Test Party (Joan Smith)": {
            "predictedRemainingValue": 500,
            "pendingValue": 0,
            "usedValue": 0,
            "remainingValue": 500,
            "initialValue": 500,
            "dataType": "currency",
            "insurancePolicyCoverageName": "Lab",
            "insuredPartyId": null,
            "insuredItemId": null,
            "assetCoverageId": "a3u3j00000HyNvYAAV",
            "assetId": "02i3j00000KhumpAAB",
            "attributeScope": "Claim Coverage",
            "attributeClass": "Limit",
            "assetTermName": "General Contents Claim Coverage Limit",
            "assetTermId": "a5N3j000000XnVtEAK",
            "claimId": "a4X3j0000001gUPEAY",
            "claimCoverageIds": ["a5G3j000000YGYwEAO"]
        }
    }
  ]
}
```

Policy Term Name: Data Cov Claim Coverage Count

Attribute Class: Limit - Scope Count

Attribute Scope: Policy Coverage Output

Name: Data Cov Claim Coverage Count

```
{ 
   "currentStanding": [
    {
        "Data Cov Claim Coverage Count": {
            "predictedRemainingValue": 3,
            "pendingValue": 1,
            "usedValue": 1,
            "remainingValue": 4,
            "initialValue": 5,
            "dataType": "number",
            "insurancePolicyCoverageName": "Lab",
            "insuredPartyId": null,
            "insuredItemId": null,  
            "assetCoverageId": "a3u3j00000HyNvVAAV",
            "assetId": "02i3j00000KhumpAAB",
            "attributeScope": "Claim Coverage",
            "attributeClass": "ScopeCountLimit",
            "assetTermName": "Data Cov Claim Coverage Count",
            "assetTermId": "a5N3j000000XnVqEAK",
            "claimId": "a4X3j0000001gUPEAY",
            "claimCoverageIds": ["a5G3j000000YGYwEAO"]
          }
    }
  ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo