---
title: "InsPolicyService:getRuleLogs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getrulelogs.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getRuleLogs

InsPolicyService:getRuleLogs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getRuleLogs

This service retrieves rule logs for a target policy, sorted by execution date in ascending order.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

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

**policyId**

 | 

Id of target policy for which to retrieve rule logs

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

See the following sample of input JSON.

```
{ 
	"policyId": "02i6g000000I21EAAS"
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

See the following sample of output JSON.

```
{
    "result": [{
        "id": <Id>,
        "objectId": <Id>,
        "stateTransitionId": <Id>,
        "stateTransitionName": <String>,
        "executionDate": <Datetime>,
        "results": [{
            "id": <Id>,
            "name": <String>,
            "condition": <String>,
            "message": <String>,
            "action": <String>,
            "result": <Boolean>,
            "details": {
                <String>: <String>
            }
        }]
    }]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Results Description

This JSON includes these key/value pairs:

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

Success message if rule condition evaluated true against target policy

Failure message if rule condition evaluated false against target policy

 |
| 

**action**

 | 

Name of action executed if rule condition evaluated true

 |
| 

**result**

 | 

Result of rule condition evaluation against target policy

 |
| 

**details**

 | 

Map of information associated with the target policy

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo