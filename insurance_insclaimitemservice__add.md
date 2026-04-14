---
title: "InsClaimItemService:add"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__add.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:add

InsClaimItemService:add[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:add

Use this service to add a claim line item to a specified claim item object.

This service can create either a Loss type claim line item or an Expense type claim line item, depending on which options get inputs.

Note

If the service receives inputs for both Loss and Expense type claim line items, it creates a Loss type claim line item.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `add`

[](https://help.salesforce.com/s?language=en_US)

## How It works

The service uses object interface field names as default input and output for common fields in both Vlocity (`ClaimLineItem__c`) and Salesforce FSC (`ClaimCoveragePaymentDetail`) data models.

-   Takes the `claimId` and gets the claim record, the associated policy record, and attribute values for both the claim and the policy.
    
-   If `type` = Loss, calls the [InsPolicyTermsService: process](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice__process.htm&language=en_US&type=5 "This service retrieves policy terms and calls the policy term's corresponding Attribute Class to process details. For the custom classes, the default method name for the attribute class is - process<Attribute>.") service.
    
    This service calculates all insured obligation amounts (copay/coinsurance, deductible, and out-of-pocket max.)
    
    If `type` = Expense, skips to step 3.
    
-   Saves the claim line item.
    
    If `type` = Expense, it is the last step the service takes.
    
-   Converts the list of insured obligation amounts returned in step 2 into child records of the claim line item as Line Adjustments record type.
    
    Note
    
    Out of pocket max is not saved as a line adjustment.
    
-   Saves the line adjustments.
    
-   Saves the insured obligation amounts and out-of-pocket max as AssetTermTrackingEntry records.
    

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

The Id of the claim the service adds a line item to.

 |
| 

`claimCoverageId`

 | 

Required.

The Id of the coverage the service uses to create this claim line item.

 |
| 

`type`

 | 

`Loss` or `Expense`

The type of claim line item to be created.

 |
| 

additionalInput

 | 

Required.

JSON of possible additional input to be saved in the Claim Line Item record or to be used in the coverage/total coverage calculation formula. It must have the following inputs:

-   `ClaimLineItem.claimAmount`
    
-   `ClaimLineItem.recipientId`
    

Uses interface field names in the input and output for common fields in Vlocity `ClaimLineItem__c` and Salesforce FSC `ClaimCoveragePaymentDetail` data models. For details, see the next table.

Any Vlocity or customer-created custom field you enter for the value of this option must follow this format, including the fully qualified field API name:

{

[](https://help.salesforce.com/s?language=en_US)`"ClaimLineItem.<fully qualified name / field API name>": "some random value",`

[](https://help.salesforce.com/s?language=en_US)`"ClaimLineItem.Customer_Custom_Field__c" : "some other random value" // customer added field`

}

Attributes prefixed with ClaimLineItem that have claim line item's API are saved to the claim line item that is created.

This JSON can also include values that calculates the claim line item's coverage amount, if the new claim line item is a Loss.

If a coverage amount or an adjusted amount or a claim amount are passed in this JSON, this service returns these amounts. It won’t recalculate them.

 |

If not listed in this table, use the fully qualified name of the field.

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

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service can take an optional `additionalInput` JSON that adds additional data to the claim line item.

Here's the format of the input JSON:

```
{ 
	"claimId: <Id>,
	"claimCoverageId: <Id>,
	"type": "Loss",
	"additionalInput": {
		"ClaimLineItem." + <fully qualified fieldname>: <values>, 
		"ClaimLineItem.claimAmount": <decimal> // example
		"ClaimLineItem.recipientId": <id> // example
		...	
		// other claim line item fields that need to be saved.
	}
}
```

And here's an example of an input JSON:

```
{ 
	"claimId": "01t000000000000001",
	"claimCoverageId": "01t000000000000002",
	"type": "Loss",
	"additionalInput": {
		"ClaimLineItem.claimAmount": 500
		"ClaimLineItem.description": "line item description"
		"ClaimLineItem.recipientId": "01t000000000000003"
	}
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of the output JSON:

```
{  
   	"adjustedAmount": <decimal>,
	"claimItemId": <id>, // if add/update,
	"claimItem" : {
		"adjustedAmount" : <decimal>,
		"description" : <string>,
		...
	}
	"childClaimItems": [
		{
			"adjustedAmount" : <decimal>,
			"adjustmentReason" : <string>
		}
	]
}
```

[](https://help.salesforce.com/s?language=en_US)Note

The `childClaimItems` node is applicable only when `type` = Loss.

Here's an example of an output JSON:

```
{  
   	"adjustedAmount": 200,
	"claimItemId": "01t000000000000004", // if add/update,
	"claimItem" : {
		"adjustedAmount" : 200,
		"description" : <string>
	},
	"childClaimItems": [
		{
			"adjustedAmount" : 200,
			"adjustmentReason" : "Deductible"
		},
		
		{
			"adjustedAmount" : 100,
			"adjustmentReason" : "Coinsurance"
		}
	]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo