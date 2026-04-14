---
title: "StateRuleService:invokeRules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__invokerules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# StateRuleService:invokeRules

StateRuleService:invokeRules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# StateRuleService:invokeRules

Use this service to invoke state transition rules associated with a target state transition on a target object. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target object to the new state.

[](https://help.salesforce.com/s?language=en_US)

Class: `StateRuleService`

[](https://help.salesforce.com/s?language=en_US)

Method: `invokeRules`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  This service retrieves the object specified by the **objectId** option.
    
2.  Based on the object type, the object's current state, and the **toState** option, the target state transition is determined.
    
3.  From the state transition, state transition rules and rule actions are retrieved and executed.
    
    [](https://help.salesforce.com/s?language=en_US)If a state transition has more than one rule, its **State Transition Completion Criteria** setting determines how the rules are evaluated:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   **Any True** specifies that at least one rule must be true for the transition to occur. This is the default.
        
    -   **All True** specifies that all rules must be true for the transition to occur.
        
4.  If the state transition rules satisfy the transition completion criteria specified on the state transition, the object is transitioned to the **toState**.
    
    [](https://help.salesforce.com/s?language=en_US)If the state transition has an action associated with it, that action is executed.
    
    [](https://help.salesforce.com/s?language=en_US)If the transition completion criteria is not satisfied, the object is transitioned to the **Alternate** state specified on the state transition if it exists. If the state transition has no **Alternate** state, the object retains its current state.
    
5.  [](https://help.salesforce.com/s?language=en_US)If the **logResults** option is specified, the results from each rule and the result of the object transaction (success or failure) is logged.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**objectID**

 | 

Required.

ID of target object

 |
| 

**toState**

 | 

Required

State to move target object to based on state transition criteria

 |
| 

**lastDefaultState**

 | 

Optional

Name of last default state of target object

 |
| 

**invokeActionType**

 | 

Optional

If specified, indicates the type of actions to invoke if criteria is fulfilled. The default setting is **default**.

**default** Only execute default actions associated with the state transition

**all** Execute all actions associated with the state transition

**none** Do not invoke any actions associated with the state transition

 |
| 

**actionScope**

 | 

Optional

If specified, indicates if invoked actions must be defined on the current state model version or on any state model versions. The default setting is **version**.

**version** Only execute actions associated with the current state model version

**any** Execute actions associated with any state model version

 |
| 

**logResults**

 | 

Optional

**true** Use to have results logged. This is the default.

**false** Use if you do not want to log results.

 |
| 

**fromNoneState**

 | 

Optional

**true** Object is transitioning from **None** state.

**false** Object is not transitioning from **None** state. This is the default.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The following sample shows state rules input JSON.

```
{ 
	"objectId": "02i3h0000009OqCAAU",
	"toState": "Review",
	"lastDefaultState": "Draft",
	"invokeActionType": "draft",
	"actionScope": "version",
	"logResults": true,
	"fromNoneState": false
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns several key/value pairs, an array of rules evaluated to false, and an array of rules evaluated to true.

```
{  
    "transition": true,
    "transitedState": "Review",
    "result": {
        "result": true,
        "ruleDetails": [{
            "result": true,
            "conditions": "Asset.Status == 'Draft'",
            "name": "Status is Draft",
            "ruleId": "a5Q6g0000005vSPEAY",
            "transitionName": "Draft > Review",
            "objId": "02i3h0000009OqCAAU"
        }, {
            "result": false,
            "conditions": "Asset.Name == 'Test'",
            "name": "Name is Test",
            "ruleId": "a5Q6g0000005vSPEAZ",
            "transitionName": "Draft > Review",
            "objId": "02i3h0000009OqCAAU"
        }]
    }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Result

**result** Overall result of executed rules. If true, the target object is transitioned to **toState**. If false, the target state remains the same or transitions to the **Alternate** state defined on the state transition.

**ruleDetails** List of the executed rules and their results

This JSON includes these key/value pairs.

| 
Key

 | 

Value

 |
| --- | --- |
| 

**result**

 | 

Result of rule condition evaluation against target object

 |
| 

**conditions**

 | 

Rule condition

 |
| 

**name**

 | 

Name of rule

 |
| 

**ruleId**

 | 

Rule Id

 |
| 

**transitionName**

 | 

Name of transition associated with rule

 |
| 

**objId**

 | 

Object ID that rules were executed against

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo