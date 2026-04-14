---
title: "StateRuleService:getTransitionStates"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__gettransitionstates.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# StateRuleService:getTransitionStates

StateRuleService:getTransitionStates[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# StateRuleService:getTransitionStates

Use this service to get default transition states, the **To** state of each from state transition, the current state, and the last default state for the target object.

[](https://help.salesforce.com/s?language=en_US)

Class: `StateRuleService`

Method: `getTransitionStates`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service retrieves the object specified by the **objectId** option.
    
2.  The service retrieves the object specified by the **objectId** option.
    
3.  The current state is retrieved from the object.
    
4.  If the object has log entries, the latest log entry is retrieved and the **lastDefaultState** value is returned as well as any associated failure messages.
    
    [](https://help.salesforce.com/s?language=en_US)If the object has no log entries, the **lastDefaultState** is returned as null and an empty list is returned for the failure messages.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**objectId**

 | 

Id of target object to retrieve state informations

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

```
{ 
    "objectId": "02i3h0000009OqCAAU"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

```
{
    "defaultTransitionStates": ["Draft", "Submitted", "Approved", "Underwriting"],
    "eachStateToStates": {
        "Underwriting": ["Approved"],
        "Submitted": ["Approved", "Decline", "Underwriting"],
        "Draft": ["Submitted"],
        "Approved": ["Issued"]
    },
    "currentState": "Submitted",
    "lastDefaultState": "Draft",
    "failureMessages": [{
        "name": "Rule 1",
        "message": "Failure Message"
    }, {
        "name": "Rule 2",
        "message": "Failure Message"
    }]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo