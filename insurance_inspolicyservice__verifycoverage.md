---
title: "InsPolicyService:verifyCoverage"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__verifycoverage.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:verifyCoverage

InsPolicyService:verifyCoverage[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:verifyCoverage

Use this service to verify valid insurance coverage for a policyholder who is filing a claim.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `verifyCoverage`

## How It Works

1.  The service takes the `DateOfLoss` and the `PerilProductCode` as entered by the user.
    
2.  Uses the `PolicyNumber` or the `PolicyHolder` and `InsuredItemName` to find the policy.
    
3.  Compares the policy effective dates with the `DateOfLoss` to verify that the loss occurred while the policy was in effect.
    
4.  Uses the `PerilProductCode` to find the `PerilProduct`, and compares the `PerilProduct` to the coverages in the policy to verify whether the `PerilProduct` is included in the coverages of this policy.
    
5.  Returns `"Covered":true` and a list of coverages if the loss is covered. Returns `"Covered":false` if the loss is not covered.
    

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

`%lossDateTime%`

or

`“YYYY-MM-DD HH:MM:SS”`

Required.

The date of the insurance policyholder's loss.

 |
| 

`PerilProductCode`

 | 

`%perilCodes:ClaimProduct%`

The code associated with the peril that the policyholder reports as what happened.

 |
| 

`PolicyNumber`

 | 

`%policyNumber%`

The policyholder's policy number.

 |
| 

`PolicyHolder`

 | 

`%PolicyHolder%`

The `asset.account.name` value.

 |
| 

`InsuredItemName`

 | 

`%InsuredItemName%`

The name of the item the policy insures. For example Toyota Prius 2018.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns a `"Covered":true/false` value. If `"Covered":true`, the service also returns a list of coverages this policy covers for this peril. The insuredItem detail includes other policy information, such as `SerialNumber` (`PolicyNumber`).

```
{
	"result": {
		"covered": true,
		"Coverages": {
			"ProductCode": "PP",
			"ProductName": "Personal Property",
			"limitCoverageC": "200000",
			"PremiumAmount": 23.9,
			"Name": "Personal Property"
		},
		"InsuredItem": {
			"ProductCode": "rentDwelling",
			"ProductName": "Rental Unit",
			"dwBuildingAge": "7",
			"dwBurglarAlarm": false,
			"dwBusUse": "office",
			"dwCentralAlarm": false,
			"dwCentralFire": false,
			"dwDeadBolt": true,
			"dwDistanceFire": "4",
			"dwSmokeDetector": true,
			"dwTerritory": "1",
			"Name": "UnitNameTest"
		},
		"SerialNumber": "RentSUPER-UN-000022-2018-",
		"Id": "02i6F000004JSuWQAW"
	}
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo