---
title: "InsClaimItemService:update"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimitemservice__update.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimItemService:update

InsClaimItemService:update[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimItemService:update

Use this service to update a claim line item to a specified claim item object.

This service can update either a Loss type claim line item or an Expense type claim line item, depending on which options to get inputs.

Note

If the service receives inputs for both Loss and Expense type claim line items, it updates the claim line item as a Loss.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimItemService`

Method: `update`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service uses object interface field names as default input and output for common fields in both Vlocity (`ClaimLineItem__c`) and Salesforce FSC (`ClaimCoveragePaymentDetail`) data models.

1.  Takes the `claimId` and the `claimItemId` and gets the claim line item record, claim record, the associated policy record, and attribute values for both the claim and the policy.
    
2.  If `type` = Loss, calls the [InsPolicyTermsService: process](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicytermsservice__process.htm&language=en_US&type=5 "This service retrieves policy terms and calls the policy term's corresponding Attribute Class to process details. For the custom classes, the default method name for the attribute class is - process<Attribute>.") service.
    
    This service calculates all insured obligation amounts (copay/coinsurance, deductible, and out-of-pocket max.)
    
    If `type` = Expense, skip to step 3.
    
3.  Updates the claim line item.
    
    If `type` = Expense, it is the last step the service takes.
    
4.  Deletes old child Line Adjustments, if any.
    
5.  Converts the list of insured obligation amounts returned in step 2 into child records of the claim line item as Line Adjustments record type.
    
    Note
    
    Out-of-pocket max isn’t saved as a line adjustment.
    
6.  Saves the new Line Adjustments.
    
7.  Saves the insured obligation amounts and out of pocket max as new AssetTermTrackingEntry records.
    

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

The Id of the claim the service updates a line item for.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`claimCoverageId`

 | 

[](https://help.salesforce.com/s?language=en_US)Required.

[](https://help.salesforce.com/s?language=en_US)The Id of the coverage the service uses to create this claim line item.

 |
| 

`claimItemId`

 | 

Required.

The Id of the claim line item the service updates.

 |
| 

`type`

 | 

Required.

Valid values for this field are `Loss` or `Expense`.

 |
| 

`additionalInput`

 | 

Required.

JSON of possible additional input to be updated in the Claim Line Item record. It must have the following inputs:

-   ClaimLineItem.claimAmount
    
-   ClaimLineItem.recipientID
    

Uses interface field names in the input and output for common fields in Vlocity `ClaimLineItem__c` and Salesforce FSC `ClaimCoveragePaymentDetail` data models. See the next table for more fields.

Any Vlocity or customer-created custom field you enter for the value of this option must follow this format, including the fully qualified field API name:

{

`"ClaimLineItem.<fully qualified name / field API name>": "some random value",`

`"ClaimLineItem.Customer_Custom_Field__c" : "some other random value" // customer added field`

}

Attributes prefixed with ClaimLineItem that have with claim line item's API are saved to the claim line item that is updated.

This JSON can also include values that calculate the claim line item's coverage amount, if the claim line item is a Loss.

If a coverage amount or an adjusted amount or a claim amount are passed in this JSON, this service will return these amounts. It will not recalculate them.

 |

If the user interface field name isn't listed in the this table, use the fully qualified name of the field.

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

This service can take an optional `additionalInput` JSON that will add additional data to the claim line item.

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

Here's a sample input JSON:

```
{ 
	"claimId": "01t000000000000001",
	"claimCoverageId": "01t000000000000002",
	"claimItemId": "01t000000000000004",
	"type": "Loss",
	"additionalInput": {
		"ClaimLineItem.claimAmount": 500
		"ClaimLineItem.description": "line item description"
		"ClaimLineItem.recipientId": "01t000000000000003",
        "ClaimLineItem.vlocity_ins__ProcedureCodeId__c": "01t000000000000004"
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

Here's a sample output JSON:

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