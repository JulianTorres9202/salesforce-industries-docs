---
title: "InsClaimService:invokeProductRules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokeproductrules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimService:invokeProductRules

InsClaimService:invokeProductRules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimService:invokeProductRules

Use this service in claim flows to invoke underwriting rules you've added to a product.

For example, if you'd added rules that send claims above a certain dollar amount to an underwriter for approval, this service invokes those rules.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimService`

[](https://help.salesforce.com/s?language=en_US)

Method: `invokeProductRules`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service finds the claim object based on the `objectID` and extracts the products for that object based on that `objectID`.
2.  Looks for the specified `transitionName`.
3.  Runs the rules associated with the product and applicable to the `transitionName`.
    
    Evaluates each Involved Party instance and/or Involved Property instance separately for each claim product rule.
    
4.  If any of the rules evaluate to true, the service executes the Vlocity action specified in those rules.
    
    For example, if the action specifies that a task be created, the service creates a task.
    
5.  Looks for the value of the `includeStateTransition` option. If the value = `true`, the service looks for the state model for this object, finds the `fieldAPIName` value, and changes that value based on the transition.
6.  Outputs the results of the evaluation for each rule on each Involved Party and/or Involved Property instance.

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

The Claim Id or Claim Coverage Id to be queried.

 |
| 

`transitionName`

 | 

The state transition name associated with the rules you want to run.

The service will run only rules associated with the `transitionName` you specify.

To find a Transition Name, go to the state model for this object.

 |
| 

`mode`

 | 

If `objectId` is a Claim Id, there are two possible `mode` values: `ItemMode` or `CoverageMode`. The `mode` parameter specifies what objects are evaluated for that Claim Id.

-   Use `ItemMode` (the default) to evaluate product rules with Applicable Type defined as Claim. The service applies these rules to every ClaimItem record associated with the Claim Id. With ItemMode , the objects that are available to the rules engine are ClaimItem and Claim objects.
    
    ItemMode is helpful for opening claim coverages at the end of a first notice of loss (for example, for the transition from Draft to Open). Imagine an auto accident involving two vehicles and three people. Any rules that evaluate as true can be used to call actions that call integration procedures to do things such as open the correct Claim Coverage for each Claim Item. Claim Coverages can include Collision for the first-party vehicle, Property Damage for the third-party vehicle, Bodily Injury for one of the drivers, and so on.
    
-   Use `CoverageMode` to evaluate product rules with Applicable Type defined as Claim Coverage. The service applies these rules to every Claim Coverage record associated with the ClaimId. With CoverageMode, the objects that are available to the rules engine are ClaimCoverage, InsurancePolicyCoverage, and Claim objects.
    
    CoverageMode is helpful when running rules against all Claim Coverages on a claim. For example, use CoverageMode when determining if any waiting period rules apply. Such rules can trigger the transition from Open to Denied.
    

If `objectId` is a Claim Coverage Id, the rules engine evaluates product rules with Applicable Type defined as ClaimCoverage. The service applies these rules to a single ClaimCoverageId. In this case, `mode` isn’t used because the service evaluates only one object, not multiple lower-level objects.

 |
| 

`falseTransitionState`

 | 

Optional.

The state the service transitions the object to when all rules run by the service evaluate to false.

The service transitions the object to this state only if `includeStateTransition` = `true`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't use anything in the input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the rule evaluation for each instance of an Involved Property and/or Involved Party.

For this example, the inputs are:

-   objectId = claimId
    
-   transitionName = rule transition name
    

```
{
    "stateTransit": " updated ClaimStatus__c from Open to Closed",
    "canTransitState": true,
    "allFalse": false,
    "falseRules": {
        "Involved Property_a3lf4000000pcFUAAY": [
            {
                "ruleDetails": {
                    "instanceKey": "Involved Property_a3lf4000000pcFUAAY",
                    "involvedItemId": "a3lf4000000pcFUAAY",
                    "requirement name": "Maximum Aggregation Rule",
                    "conditions": "Pet.petType == 'dog' AND Pet.petBreed == 'Alaskan Husky' AND ptandev2__InsuranceClaim__c.ptandev2__ClaimStatus__c == 'Open'",
                    "message": "TestMessage",
                    "action method": "Product_Rule",
                    "action class": "IntegrationProcedureService",
                    "productId": "01tf4000004mGyhAAE",
                    "transitionName": "OpenToClosed",
                    "objectId": "a3qf4000000KtfKAAS"
                }
            }
        ],
        "Involved Injury Cat Husky_a3kf4000000pLEuAAM": [
            {
                "ruleDetails": {
                    "instanceKey": "Involved Injury Cat Husky_a3kf4000000pLEuAAM",
                    "involvedItemId": "a3kf4000000pLEuAAM",
                    "requirement name": "Maximum Aggregation Rule",
                    "conditions": "Pet.petType == 'dog' AND Pet.petBreed == 'Alaskan Husky' AND ptandev2__InsuranceClaim__c.ptandev2__ClaimStatus__c == 'Open'",
                    "message": "TestMessage",
                    "action method": "Product_Rule",
                    "action class": "IntegrationProcedureService",
                    "productId": "01tf4000004mGyhAAE",
                    "transitionName": "OpenToClosed",
                    "objectId": "a3qf4000000KtfKAAS"
                }
            }
        ]
    },
    "trueRules": {
        "Involved Injury Dog Husky_a3kf4000000pLEtAAM": [
            {
                "actionResults": {
                    "IPResult": {
                        "output": "TestOutput"
                    }
                },
                "ruleDetails": {
                    "instanceKey": "Involved Injury Dog Husky_a3kf4000000pLEtAAM",
                    "involvedItemId": "a3kf4000000pLEtAAM",
                    "requirement name": "Maximum Aggregation Rule",
                    "conditions": "Pet.petType == 'dog' AND Pet.petBreed == 'Alaskan Husky' AND ptandev2__InsuranceClaim__c.ptandev2__ClaimStatus__c == 'Open'",
                    "message": "TestMessage",
                    "action method": "Product_Rule",
                    "action class": "IntegrationProcedureService",
                    "productId": "01tf4000004mGyhAAE",
                    "transitionName": "OpenToClosed",
                    "objectId": "a3qf4000000KtfKAAS"
                }
            }
        ]
    }
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

Describes what the service changed in the Status field on claim object.

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
                    "instanceKey": "Involved Property_a3lf4000000pcFUAAY",
                    "involvedItemId": "a3lf4000000pcFUAAY",
                    "requirement name": "Maximum Aggregation Rule",
                    "conditions": "Pet.petType == 'dog' AND Pet.petBreed == 'Alaskan Husky' AND ptandev2__InsuranceClaim__c.ptandev2__ClaimStatus__c == 'Open'",
                    "message": "TestMessage",
                    "action method": "Product_Rule",
                    "action class": "IntegrationProcedureService",
                    "productId": "01tf4000004mGyhAAE",
                    "transitionName": "OpenToClosed",
                    "objectId": "a3qf4000000KtfKAAS"
                }"ruleDetails": {
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
 "trueRules": {
        "Involved Injury Dog Husky_a3kf4000000pLEtAAM": [
            {
                "actionResults": {
                    "IPResult": {
                        "output": "TestOutput"
                    }
                },
                "ruleDetails": {
                    "instanceKey": "Involved Injury Dog Husky_a3kf4000000pLEtAAM",
                    "involvedItemId": "a3kf4000000pLEtAAM",
                    "requirement name": "Maximum Aggregation Rule",
                    "conditions": "Pet.petType == 'dog' AND Pet.petBreed == 'Alaskan Husky' AND ptandev2__InsuranceClaim__c.ptandev2__ClaimStatus__c == 'Open'",
                    "message": "TestMessage",
                    "action method": "Product_Rule",
                    "action class": "IntegrationProcedureService",
                    "productId": "01tf4000004mGyhAAE",
                    "transitionName": "OpenToClosed",
                    "objectId": "a3qf4000000KtfKAAS"
                }
            }
        ]
    }
```

[](https://help.salesforce.com/s?language=en_US)

## Examples

The service is typically used when you want rules to determine whether a claim can be automatically approved, or go to an underwriter for further consideration.

Did this article solve your issue?

Let us know so we can improve!

YesNo