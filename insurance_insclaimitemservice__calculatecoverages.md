---
title: "InsClaimItemService:calculateCoverages"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__calculatecoverages.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:calculateCoverages

InsClaimItemService:calculateCoverages[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:calculateCoverages

Use this service to calculate the coverage amount and adjusted amount for a claim line item. These amounts are used as payment amount when the claims adjuster pays the claim line item.

The service considers applicable deductibles, copays, coinsurance, and out-of-pocket maximums when creating adjustments.

This service evaluates the Coverage Calculation Formula if one's defined on the coverage spec.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `calculateCoverages`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service uses object interface field names as default input and output for common fields in both Vlocity (`ClaimLineItem__c`) and Salesforce FSC (`ClaimCoveragePaymentDetail`) data models.

This service works differently depending on whether a Coverage Calculation Formula exists on the coverage spec.

[](https://help.salesforce.com/s?language=en_US)When there's no Coverage Calculation Formula present, this service:

[](https://help.salesforce.com/s?language=en_US)

1.  Uses the following information to get the claim record, the associated policy record, and attribute values for both the claim and the policy.
    
    [](https://help.salesforce.com/s?language=en_US)
    -   `claimId`
        
    -   `claimCoverageId`
        
    -   `claimItemId` (if available)
        
    -   `claimAmount`
        
2.  Calls the [InsPolicyTermsService: process](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice__process.htm&language=en_US&type=5 "This service retrieves policy terms and calls the policy term's corresponding Attribute Class to process details. For the custom classes, the default method name for the attribute class is - process<Attribute>.") service.
    
    This service calculates all insured obligation amounts (copay/coinsurance, deductible, and out-of-pocket max) and returns this data.
    
3.  Subtracts the insured obligation amounts from the claim amount, if one or more insured obligation amounts exist.
    
4.  Returns the output including the final adjusted amount and child claim items (if any).
    

When a Coverage Calculation Formula exists on the coverage spec, this service:

-   Uses the following information to get the claim record, the associated policy record, and attribute values for both the claim and the policy.
    
    -   `claimId`
        
    -   `claimCoverageId`
        
    -   `claimItemId` (if available)
        
    -   `claimAmount`
        
-   Compiles the following objects (including AttributeSelectedValues <productcode.key>) to make them available to the Coverage Calculation Formula on the coverage spec:
    
    -   Claim
        
    -   Policy
        
    -   PolicyCoverage
        
    -   InsuredParty
        
    -   InsuredItem
        
    -   InvolvedInjury
        
    -   InvolvedProperty
        
-   Runs the Coverage Calculation Formula.
    
-   Calls the [InsPolicyTermsService: process](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice__process.htm&language=en_US&type=5 "This service retrieves policy terms and calls the policy term's corresponding Attribute Class to process details. For the custom classes, the default method name for the attribute class is - process<Attribute>.") service.
    
    This service calculates all insured obligation amounts (copay/coinsurance, deductible, and out-of-pocket max) and returns this data.
    
-   Subtracts the insured obligation amounts from the claim amount, if one or more insured obligation amounts exist.
    
-   Returns the output including the final adjusted amount and child claim items (if any).
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`claimId`

 | 

Required.

The Id of the claim that the service calculates the coverage amount for.

 |
| 

`claimItemId`

 | 

Optional.

Use this option when you're updating an existing claim line item with recalculated coverage and adjusted amounts.

 |
| 

`claimCoverageId`

 | 

Required.

The Id of the coverage the service calculates an amount for.

 |
| 

`additionalInput`

 | 

Required.

JSON of possible additional input for use in the coverage formulas, to be saved in the claim line item record (if saveLineItem is true). It must have the following inputs:

-   `ClaimLineItem.claimAmount`
    
-   `ClaimLineItem.recipientId`
    

 |

This option uses the interface field names described in this table in the input and output for common fields in Vlocity `ClaimLineItem__c` and Salesforce FSC `ClaimCoveragePaymentDetail` data models:

| 
User Interface Field Name

 | 

Common Fields in Vlocity `ClaimLineItem__c` and Salesforce FSC `ClaimCoveragePaymentDetail` Data Models

 |
| --- | --- |
| 

`ClaimLineItem.name`

 | 

Use for `ClaimLineItem__c.Name and` `ClaimCoveragePaymentDetail.Name`

 |
| 

`ClaimLineItem.claimAmount`

 | 

Use for `ClaimLineItem__c.ClaimAmount__c`  and `ClaimCoveragePaymentDetail.ClaimedAmount`

 |
| 

`ClaimLineItem.description`

 | 

Use for `ClaimLineItem__c.Description__c and` `ClaimCoveragePaymentDetail.Description`

 |
| 

`ClaimLineItem.recipientId`

 | 

Use for `ClaimLineItem__c.PayeeAcccountId__c`, `ClaimLineItem__c.PayeeContactId__c`, `ClaimLineItem.PayeeAccountId__c__c, and` `ClaimCoveragePaymentDetail.ClaimParticipantRecipientId`

 |
| 

`ClaimLineItem.benefitType`

 | 

Use for `ClaimLineItem__c.BenefitType__c and` `ClaimCoveragePaymentDetail.BenefitName`

 |
| 

`ClaimLineItem.reserveAmount`

 | 

Use for `ClaimLineItem__c.ReserveAmount__c`  and `ClaimCoveragePaymentDetail.ClaimCoverageReserveDetailId.ReserveAmount`

 |
| 

`ClaimLineItem.status`

 | 

Use for `ClaimLineItem__c.Status__c and` `ClaimCoveragePaymentDetail.Status`

 |
| 

`ClaimLineItem.type`

 | 

Use for `ClaimLineItem__c.Type__c and` `ClaimCoveragePaymentDetail.Type`

 |
| 

`ClaimLineItem.unitCount`

 | 

Use for `ClaimLineItem__c.Quantity__c and` `ClaimCoveragePaymentDetail.LimitUnitCount`

 |
| 

`ClaimLineItem.uom`

 | 

Use for `ClaimCoveragePaymentDetail.LimitUnitOfMeasure`

 |
| 

`ClaimLineItem.currencyIsoCode`

 | 

Use for `ClaimLineItem__c.CurrencyIsoCode` and `ClaimCoveragePaymentDetail.CurrencyIsoCode`

 |

For fields not listed here, use the fully qualified name of the field.

Attributes prefixed with ClaimLineItem that have the claim line item's API are saved to the claim line item that is created.

[](https://help.salesforce.com/s?language=en_US)

## Input JSON and Output JSON

If out-of-the-box methods of determining the adjusted amount for a payment detail meet your business needs, you can skip this section. But if you want to adjust payment detail amounts in ways that aren’t supported out of the box, this section is for you.

Typically, these out-of-the-box use cases are for scenarios not covered by power attribute classes, such as:

-   Conditional deductibles, where two deductibles exist on the same coverage spec. For example, Deductible A applies to a fire damage loss, and Deductible B applies to a flood damage loss. You want the system to determine which deductible to apply to the payment detail at runtime.
    
-   Copay/Coinsurance order of operations. For example, coinsurance and copay both exist on the same coverage spec, and you want to apply the coinsurance before applying the copay on a payment detail.
    
-   Calculation of a payout amount for a benefit type. For example, for a Wellness Visit benefit type, you want the system to calculate a $50 amount for the payment detail.
    

After you understand `InsClaimItemService: calculateCoverages` output JSON format, you can implement power attribute-like behavior to calculate payout amounts and adjustments without having an underlying power attribute class.

Before we get ahead of ourselves, let’s use a simple example to illustrate the output JSON expected to be returned by `InsClaimItemService: calculateCoverages`. Consider a straightforward use case supported by the out-of-the-box Deductible power attribute class.

Example: $5,000 claimed amount on a policy with a $1,000 deductible

Here’s the input JSON for `InsClaimItemService: calculateCoverages`.

[](https://help.salesforce.com/s?language=en_US)`{  	"claimId": "01t000000000000001", 	"claimCoverageId": "01t000000000000002", 	"claimItemId": "01t000000000000003", 	"additionalInput": { 		"ClaimLineItem.claimAmount": 5000 		"ClaimLineItem.description": "first party claim payment" 		"ClaimLineItem.recipientId": "01t000000000000004" 	} }`

Here’s the output JSON returned by `InsClaimItemService: calculateCoverages`.

[](https://help.salesforce.com/s?language=en_US)`{   	"claimItem": { 		"adjustedAmount": 4000 // loss item adjusted amount 	}, 	"claimLineItemAdjustment": { 		"attributeClass": "Deductible", // policy terms attribute class 		"adjustedAmount": 1000, // policy terms tracking entry postedAmount 		"assetTermId": "a6ERN00000000dg2AA", // policy terms id 		"remainingAmount": 0 // policy terms tracking entry remainingAmount 	} }`

Here’s how user interactions on the Financials tab invoke services, how `InsClaimItemService: calculateCoverages` gets data, and what happens to the data afterwards.

-   (1) On the Financials tab of a claim, a user clicks **New Loss Item** and enters a $5,000 claim amount. Pressing Tab to advance from Claim Amount to the next field invokes `InsClaimItemService: calculateCoverages`. In this example, the JSON output returned from `InsClaimItemService: calculateCoverages` includes these values.
    
    -   `claimLineItem: adjustedAmount` The amount paid to the payee after the deductible is subtracted from the claim amount: $5,000-$1,000=$4,000. This value is presented back to the user in the **Adjusted Amount** field on the New Loss Item form.
        
    -   `claimLineItemAdjustment:adjustedAmount` The amount of the adjustment to the claim coverage payment detail, in this case the $1,000 deductible subtracted from the claim amount.
        
    -   `claimLineItemAdjustment:attributeClass` The reason why the amount to be issued to the payee differs from the claimed amount. In our example, the claimed amount is decreased by $1,000 because a $1,000 deductible applies (attributeClass = Deductible).
        
    -   `claimLineItemAdjustment:assetTermId` The policy term for which a policy term tracking entry is created. In our example, it’s the ID of the Deductible policy term.
        
    -   `claimLineItemAdjustment:remainingAmount` The amount to set in the policy term tracking entry, in this case $0 because there’s no deductible remaining after this transaction.
        
-   (2) Clicking **Add** to save the new loss item invokes `InsClaimItemService: add`, which uses returned JSON output from `InsClaimItemService: calculateCoverages` to persist data to ClaimCoveragePaymentDetail, ClaimCoveragePaymentAdjustment, and InsurancePolicyTermTrackingEntry records. (The `InsClaimItemService: update` service works similarly.) Each record includes values related to our example:
    
    -   The ClaimCoveragePaymentDetail record has a ClaimCoveragePaymentDetail.ClaimedAmount of $5,000 and a ClaimCoveragePaymentDetail.AdjustedAmount of $4,000.
        
    -   The ClaimCoveragePaymentAdjustment record has a ClaimCoveragePaymentAdjustment.AdjustedReason of Deductible and a ClaimCoveragePaymentAdjustment.AdjustedAmount of $1,000.
        
    -   The InsurancePolicyTermTrackingEntry record has an InsurancePolicyTermTrackingEntry.PostedAmount of $1,000 and an InsurancePolicyTermTrackingEntry.RemainingAmount of $0.
        

With an understanding of the basic structure of output JSON, you can set up a more advanced use case by introducing logic into the Coverage Calculation Formula in a coverage spec.

Example: On the Details tab of a coverage spec, you enter a Coverage Calculation Formula like this, using the same ClaimLineItem syntax used for `additionalInput`.

InvokeIP('ClaimCoverage\_ClaimCoverageFormula', , INPUT('claimId', ClaimLineItem.claimId) INPUT('benefitType', ClaimLineItem.benefitType), INPUT('quantityCount', ClaimLineItem.unitCount), 'result')

At runtime, this formula calls an integration procedure called ClaimCoverage\_ClaimCoverageFormula. This integration procedure expects inputs for claimId, benefitType, and quantityCount, as shown in this sample input JSON for testing the integration procedure:

[](https://help.salesforce.com/s?language=en_US)`{  	"claimId": "a2b4W000007W2pQQAS", 	"benefitType": "Ambulance - Air", 	"quantityCount": "1", }`

The Coverage Calculation Formula specifies that output JSON for the ClaimCoverage\_ClaimCoverageFormula integration procedure is in a node called `result`. As long as the JSON structure in that `result` node conforms to the expected `InsClaimItemService: calculateCoverages` output JSON format, the system behaves exactly as if it’s using an underlying power attribute class: displaying the **Adjusted Amount** to the user and persisting data to ClaimCoveragePaymentDetail, ClaimCoveragePaymentAdjustment, and InsurancePolicyTermTrackingEntry records after the **Add** button is clicked.

In this output JSON example of a $50 payout for a Wellness Visit, the `result` node causes `InsClaimItemService: add` to perform an insert of 50 into ClaimCoveragePaymentDetail.AdjustedAmount.

[](https://help.salesforce.com/s?language=en_US)`{   	"result": { 		"claimLineItem": { 			"adjustedAmount": "50" 			} 	}, }`

Here are some tips for configuring your calculation.

-   If your use case involves existing power attribute classes, you can use `InsurancePolicyTerms: getCurrentStandings` to determine how much remains on a policy term before applying an adjustment. This step allows you to apply the correct adjustment and pass back the appropriate assetTermId. In these use cases, configure the JSON structure returned by your integration procedure to include both the claimLineItem and claimLineItemAdjustment nodes.
    
    In the claimLineItemAdjustment node, make sure to:
    
    -   Include assetTermId.
        
    -   Include attributeClass.
        
    
    The `InsClaimItemService: add` service needs both of these values to determine how to create the insurance policy term tracking entry record for that specific power attribute on the policy. For example, a coverage spec with a conditional deductible has two Deductible power attributes: Deductible A for fire and Deductible B for flood. The integration procedure within the Coverage Calculation formula can use `InsurancePolicyTerms: getCurrentStandings` to determine that Deductible A for this policy is $1,000 and Deductible B is $500. Then, based on the cause of loss for this claim, the integration procedure can figure out which deductible to apply. When returning the output JSON, make sure to return the correct assetTermId based on which deductible was applied.
    
-   Some use cases don’t involve the out-of-the-box power attribute classes but still require an adjustment to be made to the payment detail. For example, when a provider bills more than a negotiated rate, you need a ClaimCoveragePaymentAdjustment record to explain why the adjusted payment amount is less than the claimed amount. In these use cases, configure the JSON structure returned by your integration procedure to include both the claimLineItem and claimLineItemAdjustment nodes.
    
    In the claimLineItemAdjustment node:
    
    -   Leave out assetTermId because there’s no power attribute class defining this adjustment.
        
    -   Include attributeClass as the adjustment reason (for example, “Overbilling Adjustment”).
        
    
    The `InsClaimItemService: add` service uses the attributeClass string to populate the ClaimCoveragePaymentDetail.AdjustedReason field even though there’s no related attributeClass.
    
-   If a use case involves a payout amount for a benefit type, there’s no discrepancy between claimed and adjusted amounts. For example, a flat rate of $100/day applies to hospital stays. In these cases, leave the entire claimLineItemAdjustment node out of your JSON.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo