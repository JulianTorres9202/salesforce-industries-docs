---
title: "InsClaimService:invokeRules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservice__invokerules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimService:invokeRules

InsClaimService:invokeRules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimService:invokeRules

Use this service to invoke state transition rules associated with a target state transition on a target claim. If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target claim to the new state.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimService`

[](https://help.salesforce.com/s?language=en_US)

Method: `invokeRules`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  This service retrieves the object specified by the **claimId** option.
    
2.  Based on the object type, the object's current state, and the **toState** option, the target state transition is determined.
    
3.  From the state transition, state transition rules, and state transition rule actions, product rules are retrieved and executed.
    
4.  If the state transition rules satisfy the transition completion criteria specified on the state transition, the object is transitioned to the **toState**.
    
    If the state transition has an action associated with it, that action is executed.
    
    If the transition completion criteria is not satisfied, the object is transitioned to the **Alternate** state specified on the state transition if it exists. If the state transition has no **Alternate** state, the object retains its current state.
    
5.  If the **logResults** option is specified, the results from each rule and the result of the object transaction (success or failure) is logged.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**claimId**

 | 

Required

ID of target claim for which to apply rules against

 |
| 

**toState**

 | 

Required

State to move target claim to based on state transition criteria

 |
| 

**lastDefaultState**

 | 

Optional

Name of last default state of target claim

 |
| 

**invokeStateTransitionRules**

 | 

Optional

**true** Use to have state transition rules invoked. This is the default.

**false** Use if you do not want to invoke state transition rules.

 |
| 

**invokeProductRules**

 | 

Optional

**true** Use to have product rules invoked. This is the default.

**false** Use if you do not want to invoked product rules.

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

The following example shows sample input JSON.

```
{ 
    "claimId": "02i3h0000009OqCAAU",
    "toState": "Review",
    "lastDefaultState": "Draft",
    "invokeStateTransitionRules": true,
    "invokeProductRules": true,
    "invokeActionType": "draft",
    "actionScope": "version",
    "logResults": true,
    "fromNoneState": false
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The following example shows sample output JSON.

```
{ 
    "claimId": "02i3h0000009OqCAAU",
    "toState": "Review",
    "lastDefaultState": "Draft",
    "invokeStateTransitionRules": true,
    "invokeProductRules": true,
    "invokeActionType": "draft",
    "actionScope": "version",
    "logResults": true,
    "fromNoneState": false
}
```

[](https://help.salesforce.com/s?language=en_US)

## Results Description

**result** Overall result of executed rules. If true, the target object is transitioned to **toState**. If false, the target state remains the same or transitions to the **Alternate** state defined on the state transition.

**ruleDetails** List of the executed rules and their results

This JSON includes the following key/value pairs.

| 
Key

 | 

Value

 |
| --- | --- |
| 

**result**

 | 

Result of rule condition evaluation against target quote

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