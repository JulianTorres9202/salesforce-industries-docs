---
title: "InsFormularyService:getListOfCoveredDrugs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getlistofcovereddrugs.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsFormularyService:getListOfCoveredDrugs

InsFormularyService:getListOfCoveredDrugs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsFormularyService:getListOfCoveredDrugs

Use this service to get a list of brand name or generic drugs in a formulary that are part of a health plan.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsFormularyService`

Method: `getListOfCoveredDrugs`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Goes to `FormularyDrug__c` to get list of drugs covered under health plan.
    
2.  Uses `TradeName__c` and `GenericName__c` for brand name and generic drugs, respectively.
    
3.  Output `coveredDrugs` provides list of formulary drugs and corresponding details, including tier and drug details (quantity, refill limit, etc.).
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`searchText`

 | 

Required.

Search for drugs in formulary by `TradeName`, `Generic Name`, or `Drug Classification`.

 |
| 

`searchBy`

 | 

Optional.

Name or `DrugClassification`. Defaults to Name, which enables `searchText` to search for the `TradeName` or `GenericName`.

 |
| 

`effectiveDate`

 | 

Optional.

Date that drugs and formulary drugs are still in effect.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an array of covered drugs and attributes (refill limit, quantity per refill, etc.), drug providers, and drug plan tiers (i.e., copay).

```
{
	coveredDrugs: [{
		"Id": "",
		"Name": "Sample Formulary - 0023-6142",
		"FillLimitForm__c": "12 Hrs Patch",
		"HasPriorAuthorization__c": true / false,
		"HasStepTherapy__c": true / false,
		"LimitFrequency__c": "Plan Year",
		"MaxFillAllowed__c": 1,
		"QuantityPerRefill__c": 10,
		"DrugId__c": "a4b1I0000004UDaQAM",
		"DrugId__r": {
			"Id": "a4b1I0000004UDaQAM",
			"Name": "Some Drug Number",
			"TradeName__c": "RAPAFLO",
			"GenericName__c": "silodosin"
		},
		"FormularyId__c": "a4X1I000001CagBUAS",
		"FormularyId__r": {
			"Id": "a4X1I000001CagBUAS",
			"Name": "Australian Pharmaceutical Formulary",
			"LineOfBusiness__c": "Group Dental",
			"ApprovedDate__c": "2018-08-08"
		},
		"FormularyTierId__c": "a4W1I0000006q2cUAA",
		"FormularyTierId__r": {
			"Id": "a4W1I0000006q2cUAA",
			"Name": "Tier 1",
			"CoPayPercent__c": 1.2345
		}
	}, {
		...
	}]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo