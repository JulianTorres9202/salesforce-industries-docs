---
title: "InsClaimCoverageService:invokeProductRules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimcoverageservice__invokeproductrules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimCoverageService:invokeProductRules

InsClaimCoverageService:invokeProductRules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimCoverageService:invokeProductRules

Use this service when creating claim coverages to invoke product rules for state transitions.

Class: `InsClaimCoverageService`

[](https://help.salesforce.com/s?language=en_US)

Method: `invokeProductRules`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Finds the claim object based on the `objectID` and extracts the products for that object based on that `objectID`.
    
2.  Looks for the specified `transitionName`.
    
3.  Runs the rules associated with the product and applicable to the `transitionName`.
    
    Evaluates each Involved Party instance and/or Involved Property instance separately for each claim coverage product rule.
    
4.  If any of the rules evaluate to true, the service executes the Vlocity action specified in those rules.
    
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

`mode`

 | 

If set to `CoverageMode`, runs `InsuranceClaimCoverages__c` rules only.

 |
| 

`objectId`

 | 

The Claim Id to be queried.

 |
| 

`transitionName`

 | 

The state transition name associated with the rules you want to run.

The service will run only rules associated with the `transitionName` you specify.

To find a Transition Name, go to the state model for this object.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the rule evaluation for each instance of an Involved Property and/or Involved Party.

Here's the structure of the output JSON:

```
{
  "falseRules" : {
    "<String identifier>" : [
      {
        "ruleDetails": {
          "requirement name": <ProductRequirement__c.Name>,
          "conditions": <ProductRequirement__c.Conditions__c>,
          "message": <ProductRequirement__c.Message__c>,
          "action method": <ProductRequirement__c.VlocityActionId__r.InvokeMethodName__c>,
          "action class": <ProductRequirement__c.VlocityActionId__r.InvokeClassName__c>,
          "productId": <ProductRequirement__c.Product2Id__c>,
          "transitionName": <input transitionName>,
          "objectId": <input objectid>,
          "ruleId": <<ProductRequirement__c.Id>
        }
      }
    ]
  }
},  
  "trueRules": {
    "<String identifier>" : [
      {
        "ruleDetails": {
          "requirement name": <ProductRequirement__c.Name>,
          "conditions": <ProductRequirement__c.Conditions__c>,
          "message": <ProductRequirement__c.Message__c>,
          "action method": <ProductRequirement__c.VlocityActionId__r.InvokeMethodName__c>,
          "action class": <ProductRequirement__c.VlocityActionId__r.InvokeClassName__c>,
          "productId": <ProductRequirement__c.Product2Id__c>,
          "transitionName": <input transitionName>,
          "objectId": <input objectid>,
          "ruleId": <<ProductRequirement__c.Id>
        }
      }
    ]
  },
  "transitionSuccess": <Boolean, transition result>,
  "stateTransit": <message with the object's state field, the old state, and the new state.>,
  "canTransitState": <Boolean. determine if the object has fulfilled its transit criterria>,
  "allFalse": <Boolean, if no rule executed true.>
}
```

Here's an example of an output JSON with rules that have evaluated to false and rules that have evaluated to true:

```
{
  "falseRules": {
    "PetBodilyInjury_BMW 735i_a4m5w000000p6DE": [
      {
        "ruleDetails": {
          "requirement name": "Maximum Aggregation Rule",
          "conditions": "TardisCoverage.EACHPERSON == 30800",
          "message": "TestMessage",
          "action method": "Product_Rule",
          "action class": "IntegrationProcedureService",
          "productId": "01t5w00000E0L8xAAF",
          "transitionName": "OpenToClosed",
          "objectId": "a4J5w000001Z3ElEAK",
          "ruleId": "a5L5w000003Tl7EEAS"
        }
      }
    ]
  },
  "trueRules": {
    "PetBodilyInjury_BMW 735i Owner_a4m5w000000p6DE": [
      {
        "actionResults": {
          "IPResult": {
            "output": "TestOutput"
          }
        },
        "ruleDetails": {
          "requirement name": "Maximum Aggregation Rule",
          "conditions": "TardisCoverage.EACHPERSON == 30800",
          "message": "TestMessage",
          "action method": "Product_Rule",
          "action class": "IntegrationProcedureService",
          "productId": "01t5w00000E0L8xAAF",
          "transitionName": "OpenToClosed",
          "objectId": "a4J5w000001Z3EmEAK",
          "ruleId": "a5L5w000003Tl7EEAS"
        }
      }
    ]
  },
  "transitionSuccess": true,
  "stateTransit": " updated ClaimStatus__c from Open to Closed",
  "canTransitState": true,
  "allFalse": false
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo