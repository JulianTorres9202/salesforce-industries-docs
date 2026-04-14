---
title: "InsVlocityActionService:assignRecordToQueue"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insvlocityactionservice_assignrecordtoqueue.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsVlocityActionService:assignRecordToQueue

InsVlocityActionService:assignRecordToQueue[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsVlocityActionService:assignRecordToQueue

Use this service to assign a record to a specified Salesforce queue.

Class: `InsVlocityActionService`

Method: `assignRecordToQueue`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  [](https://help.salesforce.com/s?language=en_US)Takes the Id of a record and retrieves that record.
    
2.  [](https://help.salesforce.com/s?language=en_US)Using the queue name from `invokeMethodInput`, the service searches for an instance of User Group (type=`Queue`).
    
3.  [](https://help.salesforce.com/s?language=en_US)The retrieved queue is assigned as the owner of the record (`OwnerId` field value = `Salesforce queue`).
    

Note

If the Salesforce queue is configured to receive email notifications, Salesforce sends the emails to the members of the queue.

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`Id`

 | 

Required.

Id of the record for any object type.

 |
| 

`invokeMethodInput`

 | 

The `InvokeMethodInput__c` value set in the Vlocity Action instance is passed on at runtime during the execution of the Vlocity State Model.

The value must be in JSON format, with a single key-value pair. Set the key as 'queueName'. The value must be set with the name of the Salesforce queue.

```
{'queueName': 'Application Reviewers'}
```

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here is the format for the input JSON:

```
{ 
   "Id": <Application__c Id>,
   "invokeMethodInput": {"queueName": <name of user queue>}
}
```

And here's a real-life example:

```
{ 
   "Id": "a046g00000FGItyAAH",
   "invokeMethodInput": {"queueName": "Application Reviewers"}
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo