---
title: "StateRuleService:getRuleLogs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_stateruleservice__getrulelogs.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# StateRuleService:getRuleLogs

StateRuleService:getRuleLogs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# StateRuleService:getRuleLogs

Use this service to retrieve rule logs for a target object, sorted by execution date in ascending order.

[](https://help.salesforce.com/s?language=en_US)

Class: `StateRuleService`

[](https://help.salesforce.com/s?language=en_US)

Method: `getRuleLogs`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  This service retrieves logs by querying the **ObjectAppliedResult\_\_c** table to see if there are any rows with a **RecordId\_\_c** corresponding to the target object.
    
2.  If such rows exist, the service transforms the rows and returns to the caller in ascending order according to the **AppliedDateTime\_c** field.
    

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

Id of the target object for which to retrieve rule logs

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

See the following sample of input JSON.

```
{ 
	"objectId": "02i6g000000I21EAAS"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

See the following sample of output JSON.

```
{
    "result": [{
        "id": "a1a6g00000087E9AAI",
        "objectId": "02i6g000000I21EAAS",
        "stateTransitionId": "a1Z6g000000HzX1EAK",
        "stateTransitionName": "Draft to Submit",
        "executionDate": "2020-01-01T00:00:00.000Z",
        "results": [{
            "id": "a5Q6g0000005vSPEAY",
            "name": "Check Auto Year",
            "condition": "Auto.Year > 1990",
            "message": "Auto year is greater than 1990",
            "action": null,
            "result": true,
            "details": {
                "instanceKey": "2002 Toyota Camry"
            }
        }]
    }, {
        "id": "a1a6g00000087E9AAL",
        "objectId": "02i6g000000I21EAAS",
        "stateTransitionId": "a1Z6g000000HzX1EAP",
        "stateTransitionName": "Submit to Underwriting",
        "executionDate": "2020-01-05T00:00:00.000Z",
        "results": [{
            "id": "a5Q6g0000005vSPEAZ",
            "name": "Check Auto Make",
            "condition": "Auto.Make == 'Lexus'",
            "message": "Auto is a Lexus",
            "action": "Move to Underwriting",
            "result": false,
            "details": {
                "instanceKey": "2002 Toyota Camry"
            }
        }]
    }]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Results Description

This JSON includes these key/value pairs.

| 
Key

 | 

Values

 |
| --- | --- |
| 

**id**

 | 

Id of rule

 |
| 

**name**

 | 

Name of rule

 |
| 

**condition**

 | 

Rule condition

 |
| 

**message**

 | 

Success message if rule condition evaluated true against target object

Failure message if rule condition evaluated false against target object

 |
| 

**action**

 | 

Name of action executed if rule condition evaluated true

 |
| 

**result**

 | 

Result of rule condition evaluation against target object

 |
| 

**details**

 | 

Map of information associated with the target object

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo