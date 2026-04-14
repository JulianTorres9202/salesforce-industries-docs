---
title: "InsPolicyService:invokeProductRules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__invokeproductrules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:invokeProductRules

InsPolicyService:invokeProductRules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:invokeProductRules

Use this service with a policy to invoke underwriting rules you've added to a product.

For example, if you'd added rules that send certain policies to an underwriter for approval, this service invokes those rules.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)

Method: `invokeProductRules`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Finds the policy (asset) based on the `objectID` and extracts the products for that object based on that `objectID`.
    
2.  Looks for the specified `transitionName`.
    
3.  Runs the rules associated with the product and applicable to the `transitionName`
    
4.  If any of the rules evaluate to true, the service executes the Vlocity action specified in those rules.
    
    For example, if the action specifies that a task is created, the service creates a task.
    
5.  Looks for the value of the `includeStateTransition` option. If the value = true, the service looks for the state model for this object, finds the `fieldAPIName` value, and changes that value based on the transition.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`includeStateTransition`

 | 

If true, the service changes the state field specified in the state model's `fieldAPIName` to the state specified in the transition.

If false, the service does not do any state transition.

 |
| 

`objectId`

 | 

The policy (asset) Id queried.

 |
| 

`transitionName`

 | 

The state transition name associated with the rules you want to run.

The service will run only rules associated with the `transitionName` you specify.

To find a Transition Name, go to the state model for this object.

 |
| 

`falseTransitionState`

 | 

Optional.

The state the service transitions the object to when all rules run by the service evaluate to false.

The service transitions the object to this state only if `includeStateTransition` = true.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't use anything in the input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns several key/value pairs, an array of rules evaluated to false, and an array of rules evaluated to true.

```
{
	"stateTransit": " updated Status from Submit to Underwriting",
	"canTransitState": true,
	"allFalse": false,
	"falseRules": [...]
	"trueRules": [...]
	"error": "OK"
}
```

This JSON includes the following key/value pairs:

| 
Key

 | 

Value

 |
| --- | --- |
| 

`stateTransit`

 | 

Describes what the service changed in the Status field on the policy (asset) object.

 |
| 

`canTransitState`

 | 

`true` or `false`

Tells whether or not the service transitions the object to a new state.

 |
| 

`allFalse`

 | 

If all of the rules run by the service evaluate to false, `allFalse` = `true`.

If any of the rules run by the service evaluates to true, `allFalse` = `false`.

 |
| 

`falseRules`

 | 

An array of one or more `ruleDetails`.

Includes all rules run by the service that evaluate to false.

 |
| 

`trueRules`

 | 

An array of one or more `actionResults` and `ruleDetails`.

Includes all rules run by the service that evaluate to true.

Appears only if `allFalse` = `false`. That is, one or more of the rules run by the service evaluated to true.

 |
| 

`error`

 | 

Any errors encountered by the service.

If the value is ok, no error messages appear on the UI.

 |

The `falseRules` and `trueRules` arrays both include `ruleDetails` key/value pairs.

```
"ruleDetails": {
	"requirement name": "Operator Points >4",
	"conditions": "wcOperator.opPoints > 4",
	"message": "The applicant's prior citations require underwriting review prior to issuance.",
	"action method": "ReferToUnderwriting",
	"action class": "DROpenImplementationClass",
	"productId": "01tf4000001lKNQAA2",
	"transitionName": "Submit>Underwrite",
	"objectId": "0Q0f4000000ADatCAG"
}
```

The `trueRules` array includes one or more `actionResults`, additional key/value pairs, and `rulesDetails`.

The `actionResults` are the output of the Vlocity action class and action method invoked by the service.

```
"trueRules": [
	{
		"actionResults": {
			"Task_1": [
				{
					"UpsertSuccess": true,
					"Id": "00Tf400000LNkx9EAD",
					"ActivityDate": "2018-05-21",
					"WhatId": "0Q0f4000000ADatCAG",
					"Description": "The value of this vessel requires underwriting review.",
					"Subject": "Total Value"
				}
			],
			"error": "OK",
			"responseType": "SObject"
		},
		"ruleDetails": {
			"requirement name": "Total Value",
			"conditions": "WC.wcValue > 250000",
			"message": "The value of this vessel requires underwriting review.",
			"action method": "ReferToUnderwriting",
			"action class": "DROpenImplementationClass",
			"productId": "01tf4000001lKNQAA2",
			"transitionName": "Submit>Underwrite",
			"objectId": "0Q0f4000000ADatCAG"
		}
	},
}
],
```

[](https://help.salesforce.com/s?language=en_US)

## Examples

The service is typically used when you need to use rules to decide whether a policy can be automatically acted on, or it needs to go to an underwriter for further consideration. To see a working example of this service, download one of these items into your org:

-   [Watercraft Quote](https://c.na78.visual.force.com/apex/processlibraryscreen3?library=abqo0000000pasqgaw&processid=abs1n000000gmajwas&cardid=abpo00000008oznga2)
    
-   [BOP Quote](https://c.na78.visual.force.com/apex/processlibraryscreen3?library=abqo0000000pasqgaw&processid=abs1n000000cacuwas&cardid=abpo00000008ozlga2)
    

Did this article solve your issue?

Let us know so we can improve!

YesNo