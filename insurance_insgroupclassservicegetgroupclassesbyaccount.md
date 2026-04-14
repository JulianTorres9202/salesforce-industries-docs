---
title: "InsGroupClassService:getGroupClassesByAccount"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insgroupclassservicegetgroupclassesbyaccount.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsGroupClassService:getGroupClassesByAccount

InsGroupClassService:getGroupClassesByAccount[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsGroupClassService:getGroupClassesByAccount

Fetch the GroupClasses associated with the given AccountId.

Class: `InsGroupClassService`

Method: `getGroupClassesByAccount`

## How It Works

1.  The service fetches all the group classes associated with the given accountId which have an Effective Start Date less than or equal to effectiveDate and Effective End Date greater than or equal to effectiveDate.
    
2.  If effectiveDate isn't passed to the service, the service uses today's date as the effectiveDate.
    

## Inputs

| Input | Description |
| --- | --- |
| `accountId` | 
Required.

The ID of the account associated with the GroupClasses being retrieved.

 |
| `effectiveDate` | 

Optional.

Date used to determine which GroupClasses to retrieve.

 |

## Remote Options

| Option | Description |
| --- | --- |
| `accountId` | 
Required.

The ID of the account associated with the GroupClasses being retrieved.

 |
| `effectiveDate` | 

Optional.

Date used to determine which GroupClasses to retrieve.

 |

## Input JSON

Here's the sample input JSON:

```json
{
    "accountId":"001B000001UGEaRIAX",
    "effectiveDate":"dd/mm/yyyy"
}
```

## Output JSON

Here's the sample output JSON:

```json
{
    "accountId": "001B000001UGEaRIAX",
    "groupClasses":[
                {
                    "Id":"0rEB00000004CSGMA2",
                    "Name":"Manager",
                    "Code":"code01"
                },
                {
                    "Id":"0rEB00000004CO5MAM",
                    "Name":"Executive",
                    "Code": "code02"
                }
     ]
      
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo