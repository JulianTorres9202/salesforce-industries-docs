---
title: "ActionListService:processOnCreateActions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_actionlistservice__processoncreateactions.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# ActionListService:processOnCreateActions

ActionListService:processOnCreateActions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# ActionListService:processOnCreateActions

This service executes the Vlocity Action set on the State Model version of the object.

Because the **OnCreate** action is designed to execute when the object is created, this method can be called after the insert trigger of the target object. The service executes the **OnCreate** actions associated with the list of object Ids passed to it.

Or, this service can pass a map of optional parameters, which are passed to the **OnCreate** action that is going to be executed.

Note

This service is not like the other services that implement **VlocityOpenInterface2**. The signature for this service is:

```
processOnCreateActions(List<Id> objectIds, Map<String, Object> output, Map<String, Object> options
```

Class: `ActionListService`

Method: `processOnCreateActions`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  [](https://help.salesforce.com/s?language=en_US)The service takes the list of object Ids and finds the state model, state model version, and the **OnCreate** Vlocity Action associated with the state model version level.
    
2.  [](https://help.salesforce.com/s?language=en_US)The service executes the invoke method defined in the action.
    
    The input for the action is the object Id under the key "id." Example: "Id": "0Q06g000000ZE7vCAG"
    
3.  [](https://help.salesforce.com/s?language=en_US)The service passes the result of the execution in the output map with the **objectId** and **OnCreate** output.
    

[](https://help.salesforce.com/s?language=en_US)

## Input Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

**objectIds**

 | 

A list of object Ids that the user wants to sent to the **OnCreate**

 |
| 

Option map

 | 

Map of options that the user wants to send to the **OnCreate** action

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Not applicable because the input is a list of object Ids.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

See the following sample output JSON.

```
{
  "0Q06g000000ZE7vCAG": {
    "Status": "Success"
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo