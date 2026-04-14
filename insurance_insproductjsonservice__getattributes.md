---
title: "InsProductJSONService:getAttributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductjsonservice__getattributes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductJSONService:getAttributes

InsProductJSONService:getAttributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductJSONService:getAttributes

Use this service to get the attributes nodes of the ProductJSON.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsProductJSONService`

Method: `getAttributes`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service uses the `inputKey` to identify a standard product JSON with one root product as the input JSON.
2.  Filters the attributes based on these remote options:[](https://help.salesforce.com/s?language=en_US)
    -   `instanceKey`
    -   `productCode`
    -   `attributeCode`
3.  Returns an attribute node that's filtered according to the settings in step 2:
    -   If `flatten = true`, the service returns a map of attributes in the form (`attributeCode, attributeDetails`).
    -   If `flatten = false`, the service returns a list of attributes in the form (`attributeDetails`).
    -   If `flatten = true` and `valueOnly = true`, the service returns attributes in the form (`attributeCode, userValues`).

[](https://help.salesforce.com/s?language=en_US)

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

The key the service uses to get the `productJSONResult` from the input JSON.

The default value is `inputKey`.

 |
| 

`productCode`

 | 

The root product code or any child spec product code.

The service extracts attributes directly associated with the `productCode` value set.

 |
| 

`attributeCode`

 | 

Returns the attribute that matches the `attributeCode` value.

 |
| 

`instanceKey`

 | 

Extracts attributes directly associated with the product that has this `instanceKey`, and attributes of child products under the product specified by this `instanceKey`.

 |
| 

`flatten`

 | 

Returns attributes as a map in the form of (`attributeCode, attributeDetails`).

 |
| 

`valueOnly`

 | 

When used with `flatten = true`, returns attributes in the form (`attributeCode, userValues`).

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service takes a typical product JSON it identifies using the `instanceKey`, with one root product as its input.

To learn how product JSONs are structured, see [Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5 "The product JSON object provides a portable product data object for runtime use between services and templates.").

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON returns an attribute node of the product JSON found using the `inputKey = configureProduct` option, looking for attributes with `instanceKey = Jack Kirkland` and `attributeCode = lifeCoverageAmt`. Because both `flatten = true` and `valueOnly = true`, the service returns the attributes in `attributeCode:userValues` format.

```
{
	"Jack Kirkland": {
		"InsLife": {
			"lifeCoveageAmt": "500000"
		}
	},
	"error": "OK"
}
```

The next example uses the same `inputKey` as the previous example. But it has no filters set, so the service returns all attributes under each `productCode` and `instanceKey`.

```
{
	"CFACTCLONED": {
		"termLimit": 123
	},
	"Maria Kirkland": {
		"ABR": {
			"Limit-Agg": null,
			"Limit-PerOcc": "50",
			"ATTRIBUTE-074": 1200000
		},
		"ADDCOV": {
			"covBenefit": "2"
		},
		"WOP": {
			"claimWait": "90"
		},
		"InsLife": {
			"lifeCoveageAmt": "500000",
			"persSalutation": null,
			"persPhone": null,
			"persEmail": null,
			"persCountry": null,
			"persCity": null,
			"persState": null,
			"persPostalCode": null,
			"persStreet": null,
			"persAddress": null,
			"persGender": "Female",
			"persIncome": null,
			"persBMI": null,
			"persHeight": null,
			"persLastName": null,
			"persMiddleName": null,
			"persFirstName": null,
			"persWeight": null,
			"persSmoke": "N",
			"persName": null,
			"persBirthdate": "1970-09-09"
		}
	},
	"Jack Kirkland": {
		"ABR": {
			"Limit-Agg": null,
			"Limit-PerOcc": "50",
			"ATTRIBUTE-074": 1200000
		},
		"ADDCOV": {
			"covBenefit": "2"
		},
		"WOP": {
			"claimWait": "90"
		},
		"InsLife": {
			"lifeCoveageAmt": "500000",
			"persSalutation": null,
			"persPhone": null,
			"persEmail": null,
			"persCountry": null,
			"persCity": null,
			"persState": null,
			"persPostalCode": null,
			"persStreet": null,
			"persAddress": null,
			"persGender": "Male",
			"persIncome": null,
			"persBMI": null,
			"persHeight": null,
			"persLastName": null,
			"persMiddleName": null,
			"persFirstName": null,
			"persWeight": null,
			"persSmoke": "N",
			"persName": null,
			"persBirthdate": "1965-09-09"
		}
	},
	"WL-Base": {
		"covType": "10",
		"ProductCode": "WL",
		"termPayment": "check",
		"PART": "Participating",
		"termDivMeth": "reinvest",
		"payFrequency": "month",
		"featCashDividends": true,
		"featLevelPremium": true,
		"featGuaranteedBenefit": true,
		"featPolicyLoan": true,
		"featAccumCVLI": true
	},
	"error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo