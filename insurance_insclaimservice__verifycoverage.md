---
title: "InsClaimService:verifyCoverage"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__verifycoverage.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimService:verifyCoverage

InsClaimService:verifyCoverage[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimService:verifyCoverage

Use this service to verify valid insurance coverage for a policyholder who is filing a claim.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimService`

[](https://help.salesforce.com/s?language=en_US)

Method: `verifyCoverage`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the `DateOfLoss` and the `PerilProductCode` as entered by the user.
    
2.  Uses the `PolicyNumber` or the `PolicyHolder` and `InsuredItemName` to find the policy.
    
3.  Compares the policy effective dates and coverage effective dates with the `DateOfLoss` to verify that the loss occurred while the policy and associated coverage were in effect. Coverage is valid when the date of loss is within the policy effective date and the coverage effective date.
    
4.  Uses one of the following combinations of options to return different data. Returns `"Covered":true` and a list of coverages that the service found both on the peril product and on the policy.
    
    -   `DateOfLoss` + `PolicyNumber/Policyholder`:
        
        Returns all root level coverages and all insured items with their coverages.
        
    -   `DateOfLoss` + `PolicyNumber/Policyholder` + `insuredItemName` (insured):
        
        Returns all root level coverages + coverages for this `insuredItemName`
        
    -   `DateOfLoss` + `PolicyNumber/Policyholder` \+ `PerilProductCode` + `insuredItemName` (3rd party):
        
        Returns the overlapping coverages which are associated both with `PerilProduct` and the root level policy.
        
    -   `DateOfLoss` + `PolicyNumber/Policyholder` + `PerilProductCode`:
        
        Returns the overlapping coverages which are associated both with `PerilProduct` and the root level policy.
        
5.  Returns `"Covered":false` if the loss is not covered. Also returns the `policyId`, `coverageIds`, and `insuredItemId` or `InsuredPartyId`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`DateOfLoss`

 | 

`%LossDateTime%`

or

`“YYYY-MM-DD HH:MM:SS”`

Required.

The date of the insurance policyholder's loss.

 |
| 

`PerilProductCode`

 | 

`%PerilCodes:ClaimProduct%`

The code associated with the peril that the policyholder reports as what happened.

 |
| 

`PolicyNumber`

 | 

`%PolicyNumber%`

The policyholder's policy number.

If you don't enter a value for PolicyNumber, you must enter a value for `PolicyHolder`.

 |
| 

`PolicyHolder`

 | 

`%PolicyHolder%`

The `asset.account.name` value.

If you don't enter a value for PolicyHolder, you must enter a value for `PolicyNumber`.

 |
| 

`InsuredItemName`

 | 

`%InsuredItemName%`

This value can be the name of an insured item or an insured party on the policy. It can also be the name of a third party, such as an injured person or damaged property.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a `"Covered":true/false` value. If `"Covered":true`, the service also returns a list of coverages this policy covers for this peril. The insuredItem detail includes other policy information, such as `SerialNumber` (`PolicyNumber`).

If the InsuredItemName is that of an insured item or insured party in the policy, this service returns the coverages in the policy that apply to the named insured item or insured party. It also returns the `policyId`, `coverageIds`, and `insuredItemId` `orInsuredPartyId`.

The following example shows the fields available for policy holders:

```
{
  "result": {
    "covered": true,
    "Coverages": {
      "assetCoverageId": "a3n2E000005DQDVQA4",
      "AttributeSelectedValues": null,
      "PremiumAmount": null,
      "Name": "ABC Test Asset Coverage"
    },
    "policyHolderPartyId": "a0x2E00000BO3t3QAD",
    "policyHolderContactId": "0032E00002YrYj5QAF",
    "policyHolderAccountId": "0012E000022227nQAA",
    "policyId": "02i2E00000GGDGLQA5",
    "ProductCode": "SG-PPO-500-GC",
    "ProductName": "Vlocity SG - Medical Plan PPO 500",
    "AttributeSelectedValues": null,
    "SerialNumber": null,
    "Status": null
  },
  "error": "OK"
}
```

The following example shows the Coverages and Insured Items and all the fields returned for each:

```
{
  "result": [
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zrGuQAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001zrGvQAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001zrGwQAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001zrGxQAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        }
      ],
      "InsuredItem": {
        "insuredItemId": "a3o2E000002ItQUQA0",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "figure": "\"Primary\"",
        "fullname": "anik singh",
        "age": 32
        "insuredHeldProductRelationshipId": null,
        "insuredPartyId": null,
        "insuredContactId": null,
        "insuredAccountId": null
      },
      "policyId": "02i2E00000GSc9TQAT",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zpOHQAY",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001zpOIQAY",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001zpOJQAY",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001zpOKQAY",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        },
        {
          "assetCoverageId": "a3n2E000001zqwcQAA",
          "AttributeSelectedValues": null,
          "PremiumAmount": null,
          "Name": "Catastrophic disease"
        }
      ],
      "policyId": "02i2E00000GSc84QAD",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zrH4QAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001zrH5QAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001zrH6QAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        },
        {
          "assetCoverageId": "a3n2E000001zrH7QAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": null,
        "insuredContactId": null,
        "insuredPartyId": null,
        "insuredheldProductRelationshipId": "a3p2E000001iaP1QAI",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "figure": "\"Primary\"",
        "fullname": "anik singh",
        "age": 32
      },
      "policyId": "02i2E00000GSc9dQAD",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zrlfQAA",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001zrlgQAA",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001zrlhQAA",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        },
        {
          "assetCoverageId": "a3n2E000001zrliQAA",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": null,
        "insuredContactId": null,
        "insuredPartyId": null,
        "insuredheldProductRelationshipId": "a3p2E000001iaXMQAY",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "figure": "\"Primary\"",
        "fullname": "anik singh",
        "age": 32
      },
      "policyId": "02i2E00000GSc9uQAD",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zrlpQAA",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        },
        {
          "assetCoverageId": "a3n2E000001zrlqQAA",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001zrlrQAA",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001zrlsQAA",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": null,
        "insuredContactId": null,
        "insuredPartyId": null,
        "insuredheldProductRelationshipId": "a3p2E000001iaXRQAY",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "figure": "\"Primary\"",
        "fullname": "Neena Moore",
        "age": 34
      },
      "policyId": "02i2E00000GSc9zQAD",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001ztQqQAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001ztQrQAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001ztQsQAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001ztQtQAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": null,
        "insuredContactId": null,
        "insuredPartyId": null,
        "insuredheldProductRelationshipId": "a3p2E000001ibO3QAI",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "figure": "\"Primary\"",
        "fullname": "anik singh",
        "age": 34
      },
      "policyId": "02i2E00000GScRDQA1",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001ztQvQAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001ztQwQAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001ztQxQAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001ztQyQAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": null,
        "insuredContactId": null,
        "insuredPartyId": null,
        "insuredheldProductRelationshipId": "a3p2E000001ibO8QAI",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "figure": "\"Primary\"",
        "fullname": "anik singh",
        "age": 34
      },
      "policyId": "02i2E00000GScRIQA1",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001ztZoQAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001ztZpQAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001ztZqQAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001ztZrQAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": "0012E00001q2cmBQAQ",
        "insuredContactId": null,
        "insuredPartyId": "a0x2E00000BrEXVQA3",
        "insuredheldProductRelationshipId": "a3p2E000001ibODQAY",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "age": 32,
        "figure": "\"Primary\"",
        "fullname": "Test4 Test4"
      },
      "policyId": "02i2E00000GScRXQA1",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001ztZtQAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        },
        {
          "assetCoverageId": "a3n2E000001ztZuQAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001ztZvQAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001ztZwQAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": "0012E00001q2cmBQAQ",
        "insuredContactId": null,
        "insuredPartyId": "a0x2E00000BrEXVQA3",
        "insuredheldProductRelationshipId": "a3p2E000001ibOIQAY",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "age": 32,
        "figure": "\"Primary\"",
        "fullname": "Test4 Test4"
      },
      "policyId": "02i2E00000GScRcQAL",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zuDqQAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001zuDrQAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        },
        {
          "assetCoverageId": "a3n2E000001zuDsQAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001zuDtQAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": "0012E00001q2pauQAA",
        "insuredContactId": null,
        "insuredPartyId": "a0x2E00000BrQOSQA3",
        "insuredheldProductRelationshipId": "a3p2E000001ibZWQAY",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "age": 41,
        "figure": "\"Primary\"",
        "fullname": "mike moore"
      },
      "policyId": "02i2E00000GScTTQA1",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zuDvQAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001zuDwQAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        },
        {
          "assetCoverageId": "a3n2E000001zuDxQAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001zuDyQAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        }
      ],
      "InsuredItem": {
        "insuredAccountId": "0012E00001q2pauQAA",
        "insuredContactId": null,
        "insuredPartyId": "a0x2E00000BrQOSQA3",
        "insuredheldProductRelationshipId": "a3p2E000001ibZbQAI",
        "ProductCode": "HealthPerson",
        "ProductName": "HealthPerson",
        "age": 41,
        "figure": "\"Primary\"",
        "fullname": "mike moore"
      },
      "policyId": "02i2E00000GScTYQA1",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    },
    {
      "covered": true,
      "Coverages": [
        {
          "assetCoverageId": "a3n2E000001zuE0QAI",
          "ProductCode": "C001067001",
          "ProductName": "CATASTROPHIC DISEASES",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1827.19,
          "Name": "CATASTROPHIC DISEASES"
        },
        {
          "assetCoverageId": "a3n2E000001zuE1QAI",
          "ProductCode": "C001001155",
          "ProductName": "PLENO",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "PLENO"
        },
        {
          "assetCoverageId": "a3n2E000001zuE2QAI",
          "ProductCode": "C001066001",
          "ProductName": "Foreign Assistance",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1801.77,
          "Name": "Foreign Assistance"
        },
        {
          "assetCoverageId": "a3n2E000001zuE3QAI",
          "ProductCode": "C001096001",
          "ProductName": "DENTAL PREMIUM",
          "AttributeSelectedValues": null,
          "PremiumAmount": 1350.53,
          "Name": "DENTAL PREMIUM"
        }
      ],
      "policyId": "02i2E00000GScTdQAL",
      "ProductCode": "001001155",
      "ProductName": "ALFA HEALTH PLAN - PLENO",
      "DedSi": false,
      "SumIns": "600000",
      "Deductible01": "15000",
      "Coinsurance01": "0 - $65,000.00",
      "CHMQ01": "0",
      "Frequency01": "Anual",
      "SerialNumber": "001001155--2020-",
      "Status": "InForce"
    }
  ],
  "error": "OK"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Examples

The service is typically used in claims flows to verify that a policyholder has valid coverage before a claim is created.

Did this article solve your issue?

Let us know so we can improve!

YesNo