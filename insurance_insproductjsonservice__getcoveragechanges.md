---
title: "InsProductJSONService:getCoverageChanges"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__getcoveragechanges.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductJSONService:getCoverageChanges

InsProductJSONService:getCoverageChanges[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductJSONService:getCoverageChanges

Use this service for renewals, to get the coverage changes between two product JSONs. You can use the resulting difference map for display in the UI, or in a generated document.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsProductJSONService`

Method: `getCoverageChanges`

The service returns changed coverages as well as added and removed coverages, and highlights changes in attributes.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Uses the value of `inputKey1` to find one product JSON that contains coverages for comparison.
    
2.  Uses the value of `inputKey2` to find another product JSON that contains the coverages for comparison.
    
3.  Returns a change map that highlights selected optional coverages, unselected optional coverages, and changes in attribute `userValues`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`inputKey1`

 | 

Identifies the first product JSON for comparison.

Default = `inputKey1`

 |
| 

`inputKey2`

 | 

Identifies the second product JSON for comparison.

Default = `inputKey2`

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service takes two typical product JSONs.

To learn how product JSONs are structured, see [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.").

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a difference map that includes coverages added and removed from the policy and coverages with different attribute values.

If the policy includes grandchild-level coverage differences, these appear in the difference map under the `productCode` or `instanceKey`.

These are the different keys in the difference map:

| 
Key

 | 

Description

 |
| --- | --- |
| 

`addedCoverages`

 | 

List of coverages in the first product JSON but not in the second product JSON.

 |
| 

`removedCoverages`

 | 

List of coverages not in the first product JSON but in the second product JSON.

 |
| 

`selectedCoverages`

 | 

List of selected coverages in the first product JSON but not selected in the second product JSON.

 |
| 

`unselectedCoverages`

 | 

List of selected coverages not in the first product JSON but selected in the second product JSON.

 |
| 

`changedCoverages`

 | 

List of coverages in the first product JSON with different attribute userValues in the second product JSON.

 |

```
{
	"result": {
		"root": {
			"addedCoverages": [{
				"displaySequence": 8,
				"Id": "01t1J00000AvEx5QAF",
				"Name": "BoCovNoAttr1",
				"ProductCode": "BCNA1",
				"IsRecommended__c": false,
				"RecordTypeName__c": "CoverageSpec",
				"IsConfigurable__c": false,
				"productId": "01t1J00000AvEx5QAF",
				"pciId": "a1x1J0000043KKDQA2",
				"isOptional": false,
				"isSelected": true,
				"attributeCategories": {
					"totalSize": 0
				}
			}],
			"unselectedCoverages": [{
				"attributeCategories": {
					...
				}
				"isSelected": true,
				"isOptional": false,
				"ImageId": "/sfc/servlet.shepherd/version/renditionDownload?rendition=ORIGINAL_Png&versionId=0681J000002tD9wQAE",
				"pciId": "a1x1J000002FPmwQAG",
				"productId": "01t1J000009rd2ZQAQ",
				"IsConfigurable__c": true,
				"RecordTypeName__c": "CoverageSpec",
				"PricingSource__c": "premiumCamera__premiumCamera",
				"IsRecommended__c": false,
				"LineOfBusiness__c": "Property & Casualty",
				"ProductCode": "C",
				"Family": "Personal Lines",
				"Name": "Camera",
				"Id": "01t1J000009rd2ZQAQ",
				"displaySequence": 7
			}],
			"selectedCoverages": [{
				"displaySequence": 2,
				"Id": "01t1J000009rd2VQAQ",
				"Name": "Jewelry",
				"Family": "Personal Lines",
				"ProductCode": "J",
				"IsRecommended__c": false,
				"PricingSource__c": "premiumJewelry__premiumJewelry",
				"RecordTypeName__c": "CoverageSpec",
				"IsConfigurable__c": true,
				"productId": "01t1J000009rd2VQAQ",
				"pciId": "a1x1J000002bVjvQAE",
				"ImageId": "/servlet/servlet.FileDownload?file=00P1J00000YMFBZUA5",
				"eligibilityCriteria": "X.limitCovX > 3000",
				"isOptional": true,
				"isSelected": true,
				"attributeCategories": {
					...
				}
			}],
			"changedCoverages": [{
						"changedAttributes": {
							"limitCoverageC": {
								"newValue": "200000",
								"oldValue": "100000"
							}
						}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo