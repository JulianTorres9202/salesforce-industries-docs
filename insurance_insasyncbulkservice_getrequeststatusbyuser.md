---
title: "InsAsyncBulkService:getRequestStatusByUser"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insasyncbulkservice_getrequeststatusbyuser.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsAsyncBulkService:getRequestStatusByUser

InsAsyncBulkService:getRequestStatusByUser[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsAsyncBulkService:getRequestStatusByUser

Use this service to get the status of async bulk requests and information about the associated async request items.

Class: `InsAsyncBulkService`

Method: `getRequestStatusByUser`

## How It Works

1.  The service takes the userId, accountId, or request names as input.
2.  The service then retrieves the active async bulk requests.
3.  The service populates the outputMap with the details of the active request.
4.  The service then retrieves the data of associated async bulk request item records and populates the `requestItems` node for each async request.
5.  If `isAdditionalInfo` flag is set to `true`, then the service adds the **AdditionalInformation** field of each respective async request entity to the outputMap.
6.  The service then generates the outputMap.

## Input Options

| Input | Description |
| --- | --- |
| `userId` | 
Optional

Id of the async bulk request user

 |
| `accountId` | 

Optional

Id of the async bulk request account

 |
| `names` | 

Optional

List of async bulk request names

 |
| `isAdditionalInfo` | 

Optional

If `isAdditionalInfo` is set to `true`, then the **AdditionalInfo** field of respective async request entity is added to the outputMap.

 |

## Input JSON

Here's the sample input JSON when `isAdditionalInfo` parameter is set to `false`:

```json
{      
    "userId": "0rfxx000000001dAAA",
    "accountId": "001xx000000001dAAA",
    "names" : ["Insurance_Enrollment"],
    "isAdditionalInfo": false
}
```

## Output JSON

Here's the sample output JSON when `isAdditionalInfo` parameter is set to `false`:

```json

{  
    "requestDetails":[{
            "name": "Insurance_Enrollment",
            "createdDate": "Thu Nov 16 05:23:06 GMT 2023",
            "status": "Completed",
            'jobCount": 3,
            'pendingJobCount": 0,
            "successfulJobCount": 1,
            "failedJobCount": 2,
            "cancelledJobCount": 0,
            "erroredJobCount": 0,
            "requestItems" : [{
                 "status": "Completed",
                 "planName": "Dental Premium",
                 "batchJobId": "18cSG00000UfdYAE",
                 "id": "18cxx0000004DUuAAM"
               },
               {
                 "status": "Completed",
                 "planName": "VSP Premium",
                 "batchJobId": "18cSG00000UfdYAA",
                 "id": "18cxx0000004DUuMAA"
               }]
             }]
}
```

## Input JSON

Here's the sample input JSON when `isAdditionalInfo` parameter is set to `true`:

```
{      
    "userId": "0rfxx000000001dAAA",
    "accountId": "001xx000000001dAAA",
    "names" : ["Insurance_Enrollment"],
    "isAdditionalInfo": true
}
```

## Output JSON

Here's the sample output JSON when `isAdditionalInfo` parameter is set to `true`:

```json
{        
    "requestDetails":
            [{
            "name": "Insurance_Enrollment",
            "createdDate": "Thu Nov 16 05:23:06 GMT 2023",
            "status": "Completed",
            'jobCount": 3,
            'pendingJobCount": 0,
            "successfulJobCount": 1,
            "failedJobCount": 2,
            "cancelledJobCount": 0,
            "erroredJobCount": 0,
            "additionalInformation":{
                "batchJobDetails":[{
                            "batchJobId":"0mdxx0000000001AAA",
                            "productName":"prod1",
                            "productId":"0rk1000000001dAAA"
                                  }]
                }
            "requestItems" : [{
                 "status": "Completed",
                 "planName": "Dental Premium",
                 "batchJobId": "18cSG00000UfdYAE",
                 "id": "18cxx0000004DUuAAM"
                },
                {
                  "status": "Completed",
                  "planName": "VSP Premium",
                  "batchJobId": "18cSG00000UfdYAA",
                  "id": "18cxx0000004DUuMAA"
                }]
            }]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo