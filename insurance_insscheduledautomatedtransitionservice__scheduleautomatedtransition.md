---
title: "InsScheduledAutomatedTransitionService:scheduleAutomatedTransition"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insscheduledautomatedtransitionservice__scheduleautomatedtransition.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsScheduledAutomatedTransitionService:scheduleAutomatedTransition

InsScheduledAutomatedTransitionService:scheduleAutomatedTransition[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsScheduledAutomatedTransitionService:scheduleAutomatedTransition

Use this service to automate the state transition by scheduling an object state transition, from an origin state to a target state (Vlocity States), using hourly, daily, or weekly patterns.

Class: `InsScheduledAutomatedTransitionService`

Method: `scheduleAutomatedTransition`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This transition is for Vlocity State Model workflows. Complex scheduling patterns (every two days, every first Monday of the month, etc.) are not supported.

1.  With the objectName and fieldName (and the optional typeName and typeValue) inputs, the specific Vlocity State Model Version that represents the workflow is determined.
    
2.  With the fromState and toState inputs, the specific Vlocity State Transition within that workflow, i.e, within the Vlocity State Model Version from the previous step, is determined. The schedule inputs provide information on how often and when to run a Salesforce scheduled job that would perform the automated state transition, from the 'fromState' to 'toState'. Every time the scheduled job runs, it performs these actions:
    
    1.  Retrieve up to 5 instances of the type represented by 'objectName', where the value of the field represented by 'fieldName' = the value represented by 'fromState'. This ensures that only those object instances that are currently in the state represented by the 'fromState' are picked for performing the transition.
        
    2.  All the configured Vlocity State Transition rules for the specified Vlocity State Transition (as determined from Step 2 above) are executed.
        
    3.  If the overall result from the rule execution (which is governed by the Transition Completion Criteria set on the Vlocity State Transition) is true, such as the rule execution passed, the object instance's state is updated to the state and represented by the 'toState'.
        
    4.  If the overall result from the rule execution is false, i.e. the rule execution failed, then the object instance's state is updated to the Alternate state configured in the Vlocity State Transition if it exists.
        
    5.  If the object instance's state gets updated to a new state (either 'toState' or the Alternate state for the specified Transition), the corresponding Vlocity Actions configured for that state (i.e. the 'To State' field in Vlocity Action) are executed.
        
    6.  The number of object instances whose state was updated to 'toState' is returned in 'noOfUpdatedRecords'. The number of object instances whose state was updated to the Alternate state is returned in 'noOfUpdatedRecordsToAlternateStates'.
        
    7.  If no transition was performed, the object instance remains in the 'fromState'.
        

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`objectName`

 | 

Required.

Object API name

 |
| 

`fieldName`

 | 

Required.

Field API name that hosts the state value.

 |
| 

`fromState`

 | 

Required.

From State (origin) field value of the state transition.

 |
| 

`toState`

 | 

Required.

To State (target) field value of the state transition.

 |
| 

`typeName`

 | 

Optional.

`typeName` represents the value for the`typeFieldName_c`field from Vlocity State Model. This is the name of a field from another object for which a given Vlocity State Model instance is being configured for. For example, this could be set as 'Type\_\_c' field for the object 'Application\_\_c'.

 |
| 

`typeValue`

 | 

Optional.

`typeValue`represents the value for the`typeFieldValue_c`field from Vlocity State Model. This is a specific value for the field represented by the 'typeName' input. The combination of <typeName, typeValue> is used to select a specific Vlocity State Model.

Note

For example, with typeName = 'Type\_\_c' and typeValue = 'Individual Provider', a specific Vlocity State Model configured for Application\_\_c object will be used.







 |
| 

`schedule`

 | 

A map object that contains `pattern`, `startTime`, and `dayOfTheWeek` keys (see below) to schedule when the transition will execute.

 |
| 

`schedule.pattern`

 | 

Required.

String value

`HOURLY`, `DAILY`, or `WEEKLY`.

 |
| 

`schedule.startTime`

 | 

Format: HH:MM, military time.

Not required if `schedule.pattern` = `HOURLY`.

 |
| 

`schedule.dayOfTheWeek`

 | 

String value.

Acceptable values: `SUN`, `MON`,`TUE`, `WED`, `THU`, `FRI`, or `SAT`.

Days can also be represented numerically, from 1 to 7, where Sunday = `1`, Monday = `2`, etc.

Required if `schedule.pattern` = `WEEKLY`.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's an example of the input JSON whose schedule pattern is weekly at 13:30 every Monday:

```
{ 
   	"objectName":"prefix__Application__c",
  	"fieldName":"prefix__Status__c",
	"fromState":"New",
	"toState":"Submitted",
	"schedule":{
		"pattern":"WEEKLY",
		"startTime":"13:30",
		"dayOfTheWeek":"MON"
	}
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON shows the number of records updated (maximum five) and lists any exceptions.

```
{
"noOfRecordsForProcessing": <Number of records for processing from a search, max=5>,
"noOfUpdatedRecords": <Number of records that have successful 'from state' to 'to state' transition>,
"noOfUpdatedRecordsToAlternateStates": <Number of records that have successful 'from state' to 'alternate state' transition>,
"errors":<Consolidated error mapping between record ID and error detail. This is null when there's no error.>
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo