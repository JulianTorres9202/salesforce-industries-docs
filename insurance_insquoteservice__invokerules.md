---
title: "InsQuoteService:invokeRules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__invokerules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsQuoteService:invokeRules

InsQuoteService:invokeRules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:invokeRules

Use this service to Invoke state transition rules associated with a target state transition on a target quote.

If the rules satisfy the transition criteria, this service executes actions associated with the transition, optionally logs the results of the rule executions, and transitions the target quote to the new state.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

Before this service runs, the system runs a guest user check.

This service can be used by guest users. A guest user who's running an OmniScript, Integration Procedure, or UI task will be able to continue; this service will run. However, the `quoteId` and `opportunityId` are encrypted in these cases, so guest users cannot see these Ids.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

[](https://help.salesforce.com/s?language=en_US)

Method: `invokeRules`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  This service retrieves the object specified by the **quoteId** option.
    
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

**quoteID**

 | 

Required.

[](https://help.salesforce.com/s?language=en_US)The `QuoteId`, or the encrypted `QuoteId` if the request is for a customer or guest user.

 |
| 

**toState**

 | 

Required

State to move target quote to based on state transition criteria

 |
| 

**lastDefaultState**

 | 

Optional

Name of last default state of target quote

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
    "quoteId": "02i3h0000009OqCAAU",
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
    "transition": true,
    "transitedState": "Review",
    "stateTransitionRules": {
        "result": true,
        "ruleDetails": [{
            "result": true,
            "conditions": "Quote.Status == 'Draft'",
            "name": "Status is Draft",
            "ruleId": "a5Q6g0000005vSPEAY",
            "transitionName": "Draft > Review",
            "objId": "02i3h0000009OqCAAU"
        }, {
            "result": false,
            "conditions": "Quote.Name == 'Test'",
            "name": "Name is Test",
            "ruleId": "a5Q6g0000005vSPEAZ",
            "transitionName": "Draft > Review",
            "objId": "02i3h0000009OqCAAU"
        }]
    },
    "productRules": {
        "allFalse": false,
        "trueRules": {
            "Quote": [{
                "ruleDetails": {
                    "ruleId": "a5Q6g0000005vSPEBX",
                    "objectId": "02i3h0000009OqCAAU",
                    "transitionName": "Draft > Review",
                    "productId": "01t6g000000RzFAAA0",
                    "action class": null,
                    "action method": null,
                    "message": "Name is not blank",
                    "conditions": "Quote.Name != ''",
                    "requirement name": "Name is not blank"
                } 
            }]
        },
        "falseRules": {
            "Quote": [{
                "ruleDetails": {
                    "ruleId": "a5Q6g0000005vSPEBX",
                    "objectId": "02i3h0000009OqCAAU",
                    "transitionName": "Draft > Review",
                    "productId": "01t6g000000RzFAAA0",
                    "action class": null,
                    "action method": null,
                    "message": "Name is blank",
                    "conditions": "Quote.Name == ''",
                    "requirement name": "Name is blank"
                } 
            }]
        }
    }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Result Description

**result** Overall result of executed rules. If true, the target object is transitioned to **toState**. If false, the target state remains the same or transitions to the **Alternate** state defined on the state transition.

**ruleDetails** List of the executed rules and their results

This JSON includes these key/value pairs:

| 
Key

 | 

Value

 |
| --- | --- |
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

**objId**

 | 

Object ID that rules were executed against

 |
| 

**result**

 | 

Result of rule condition evaluation against target quote

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

Did this article solve your issue?

Let us know so we can improve!

YesNo