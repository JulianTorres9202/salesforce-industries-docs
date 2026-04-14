---
title: "InsPolicyService:getInsuredItems"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getinsureditems.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getInsuredItems

InsPolicyService:getInsuredItems[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getInsuredItems

Use this service to find and return insured items and insured parties from a policy (asset).

You can use this service in OmniScripts and Integration Procedures for modifying and canceling policies, to get the insured items and insured parties available in the current policy.

You can get a specific insured item, a subset of insured items, or all of them, based on your options.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `getInsuredItems`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Uses the `assetId` or `policyId` to find the policy (asset) to search.
    
2.  Finds the insured item object and/or held product relationship object (insured parties) associated with the policy. If `productCode` and/or `instanceKey` are specified, finds only those insured items or insured parties that have the specified code or key.
    
3.  Returns a JSON that contains the attributes of the insured items and insured parties, and their instance keys.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`assetId` or `policyId`

 | 

Required.

```
%theIdYouNeed%
```

The Id of the asset (policy) the service will get insured items for.

 |
| 

`getDataDRBundleName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| 

`getDataCustomClass`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| 

`productCode`

 | 

Optional.

The service returns only the insured items or insured parties that match this code.

Use this option when you want to be able to specify only certain insured items or insured parties.

 |
| 

`instanceKey`

 | 

Optional.

The service returns only the insured item or insured party that matches this key.

Use this option when you want to be able to specify only one item.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a JSON that contains an array of insured parties and insured items by product code.

In this example, only an `assetId` was specified, so all insured items are returned.

```
{
	"error": "OK",
	"Step1": {
		"AUTO": [{
				"VehicleType": "PASSENGER CAR",
				"isPrimary": true,
				"isParent": true,
				"autoInstanceKey": "2015 Lexus LX250",
				"est_annual_mileage": "1-10000",
				"BodyClass": "Sedan/Saloon",
				"autoYear": 2015,
				"autoModel": "LX250",
				"autoLicNum": "Lexus",
				"autoAntiTheft": false
			},
			{
				"VehicleType": "MULTIPURPOSE PASSENGER VEHICLE (MPV)",
				"isPrimary": true,
    				"isParent": true,
				"autoInstanceKey": "2006 Honda Odyssey",
				"est_annual_mileage": "1-10000",
				"BodyClass": "Minivan",
				"autoYear": 2006,
				"autoModel": "Odyssey",
				"autoLicNum": "Honda",
				"autoAntiTheft": false
			},
			{
				"VehicleType": "PASSENGER CAR",
				"isPrimary": true,
				"isParent": true,
				"autoInstanceKey": "2018 530 BMW",
				"est_annual_mileage": "1-10000",
				"BodyClass": "Sedan/Saloon",
				"autoYear": 2018,
				"autoModel": "BMW",
				"autoLicNum": "530",
				"autoAntiTheft": false
			},
			{
				"VehicleType": "PASSENGER CAR",
				"isPrimary": true,
                                "isParent": true,
				"autoInstanceKey": "2016 Camry Toyota",
				"est_annual_mileage": "1-10000",
				"BodyClass": "Sedan/Saloon",
				"autoYear": 2016,
				"autoModel": "Toyota",
				"autoLicNum": "Camry",
				"autoAntiTheft": false
			}
		],
		"DRIVER": [{
				"LN": "Smith",
				"LastName": "Smith",
				"isPrimary": false,
                                "isParent": false,
				"driverInstanceKey": "Joan Smith",
				"GENDER": "Female",
				"FN": "Joan",
				"FirstName": "Joan",
				"AGE": 20
			},
			{
				"LN": "Smith",
				"LastName": "Smith",
				"isPrimary": false,
                                "isParent": false,
				"driverInstanceKey": "John Smith",
				"GENDER": "Male",
				"FN": "John",
				"FirstName": "John",
				"AGE": 30
			},
			{
				"LN": "Henderson",
				"LastName": "Henderson",
				"isPrimary": false,
                                "isParent": false,
				"driverInstanceKey": "Robert Henderson",
				"GENDER": "Male",
				"FN": "Robert",
				"FirstName": "Robert",
				"AGE": 30
			},
			{
				"LN": "Schell",
				"LastName": "Schell",
				"isPrimary": false,
                                "isParent": false,
				"driverInstanceKey": "Kinsey Schell",
				"GENDER": "Female",
				"FN": "Kinsey",
				"FirstName": "Kinsey",
				"AGE": 20
			}
		]
	}
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo