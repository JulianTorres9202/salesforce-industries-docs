---
title: "InsPolicyTermsService: process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice__process.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyTermsService: process

InsPolicyTermsService: process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyTermsService: process

This service retrieves policy terms and calls the policy term's corresponding **Attribute Class** to process details. For the custom classes, the default method name for the attribute class is - process<Attribute>.

`Class`: InsPolicyTermsService

`Method`: process

Important

With the Insurance Summer '21 release, the same service supports processing of PowerAttributes for these Salesforce FSC Claim Data Objects:

-   Claim
    
-   ClaimCoverage
    
-   ClaimCoverageReserveDetail
    
-   ClaimCoveragePaymentDetail
    
-   ClaimCoveragePaymentAdjustment
    

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Based on the inputs **claimId** and **claimCoverageId**, retrieves the policy and policy terms details such as Policy Id, Policy Coverage Id, Insured Id, and Involved Id.
    
2.  The Attribute Class/es is/are instantiated
    
    -   For the ClaimLineItemClaimedAmountEntered applicable action flow:
        
        Attribute Classes (if available) are called sequentially each time passing updated parameters, especially the requested amount. The sequence is **Deductible: Out of Pocket Max** then **Copay or Coinsurance: Out of Pocket Max**.
        
    -   [](https://help.salesforce.com/s?language=en_US)
        
        For the PaymentAttempted flow and ReserveAdjustmentAttempted flows:
        
        Power attributes of the same attribute classes are collected and checked together. The service throws an error if the requested amount exceeds any one of the limits.
        
3.  Returns data for the policy term to the function that called the service.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**claimItemData**

 | 

List of objects containing the individual claimCoverage or claimItem details. The list includes:

**claimId** Required.

**claimCoverageId** Required.

**isCancelled** Required. Set the default value to false. Set it to true only for cancelled payment scenarios. For all other scenarios, set it to false.

**claimItemId** Optional. Only if applicableAction is **ClaimLineItemClaimedAmountEntered** for editing or deleting the loss item

**newReserveAmount** Optional. Only if applicableAction is **ReserveAdjustmentAttempted** when opening a claim coverage in coverage reserve mode or creating or editing a loss item for a claim coverage in Reserve Worksheet mode.

**requestedAmount** Optional. The **AdjustedAmount\_\_c** for the claimItem

**isOpenCoverage** Optional. True when opening a claim coverage. False when used in a claim item or when updating an existing claim coverage.

**isValidation** Optional. Only if applicableAction is **PaymentAttempted**. True when it occurs before invoking the **ClaimInitialPaymentIP**. False when this occurs after invoking the **ClaimPaymentIP**.

 |
| 

**applicableAction**

 | 

Choose one of the following values for the **Attribute\_\_c.ApplicableAction\_\_c** field:

-   **ClaimLineItemClaimedAmountEntered**
    
-   **PaymentAttempted**
    
-   **ReserveAdjustmentAttmpted**
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format of the input JSON:

```
{ 
   "claimItemData" : [
		{
			"claimId" : <id>,
			"claimCoverageId" : <id>,
			"claimItemId" : <id>,
			"oldReserveAmount" : <decimal>, 
			"newReserveAmount" : <decimal>, 
			"requestedAmount" : <decimal>, 
			"isOpenCoverage" : <boolean> ,
			"isValidation" : <boolean>
		}
	]
}
```

Here's a sample input JSON:

```
{  
   "claimItemData" : [
		{
			"claimId" : 01t000000000000001"",
			"claimCoverageId" : "01t000000000000002",
			"claimItemId" : "01t000000000000003",
			"oldReserveAmount" : 0, 
			"newReserveAmount" : 1000, 
			"requestedAmount" : 500, 
			"isOpenCoverage" : false
		}
	]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of the output JSON for the ClaimLineItemClaimedAmountEntered applicable action:

```
{  
   "newEntriesDetails": [
        {
            "remainingValue": <decimal>,
            "postedValue": <decimal>,
            "calculatedInitialValue": <decimal>,
            "attributeScope": <string>,
            "claimItemId": <id>,
            "assetTermName": <string>,
            "attributeCode": <string>,
            "attributeClass": <string>,
            "initialAmount": <decimal>,
            "initialValue": <decimal>,
            "insuredPartyId": <id>,
            "insuredItemId": <id>,
            "involvedPropertyId": <id>,
            "involvedInjuryId": <id>,
            "claimCoverageId": <id>,
            "claimId": <id>,
            "assetTermId": <id>,
            "name": <string>
        },
        { ... },
        { ... }
    ]
}
```

Here's an example of an output JSON for the ClaimLineItemClaimedAmountEntered applicable action:

```
// note: same claim, claim coverage, insured party, involved property. 
// different policy terms details (asset term id, asset term name), term tracking details (initialValue, calculatedInitialValue, postedValue, remainingValue)

{  
   "newEntriesDetails": [
        {
            "remainingValue": 0,
            "postedValue": 50,
            "calculatedInitialValue": 50,
            "attributeScope": "Claim",
            "claimItemId": null,
            "assetTermName": "Deductible Terms",
            "attributeCode": "d6534444-89c9-dbf3-6591-595066dd802e",
            "attributeClass": "Deductible",
            "initialAmount": null,
            "initialValue": 50,
            "insuredPartyId": "01t000000000000001",
            "insuredItemId": null,
            "involvedPropertyId": "01t000000000000002",
            "involvedInjuryId": null,
            "claimCoverageId": "01t000000000000003",
            "claimId": "01t000000000000004",
            "assetTermId": "01t000000000000005",
            "name": "Deductible (Claim)"
        },
        {
            "remainingValue": 50,
            "postedValue": 50,
            "calculatedInitialValue": 50,
            "attributeScope": "Claim",
            "claimItemId": null,
            "assetTermName": "Copay Terms",
            "attributeCode": "atCopay",
            "attributeClass": "Copay",
            "initialAmount": null,
            "initialValue": 100,
            "insuredPartyId": "01t000000000000001",
            "insuredItemId": null,
            "involvedPropertyId": "01t000000000000002",
            "involvedInjuryId": null,
            "claimCoverageId": "01t000000000000003",
            "claimId": "01t000000000000004",
            "assetTermId": "01t000000000000007",
            "name": "Copay (Claim)"
        }
    ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo