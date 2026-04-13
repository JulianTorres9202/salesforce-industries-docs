---
title: "InsAsyncBulkService:getRequestStatusById"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insasyncbulkservice_getrequeststatusbyid.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsAsyncBulkService:getRequestStatusById

InsAsyncBulkService:getRequestStatusById[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsAsyncBulkService:getRequestStatusById

Use this service to get the status of the async bulk request and its details associated with the request.

Class: `InsAsyncBulkService`

Method: `getRequestStatusById`

## How It Works

1.  The service takes the Id of insurance async bulk request as input.
2.  The service then retrieves the details of async bulk request whose Id is provided as input.
3.  The service populates the output map with the request details.
4.  If `isAdditionalInfo` paramater is set to `true`, the service adds the **AdditionalInformation** field value of the bulk request to the outputMap.
5.  The service then generates the output map.

## Input Options

| Input | Description |
| --- | --- |
| `requestId` | 
Required

The ID of the insurance async bulk request

 |
| `isAdditionalInfo` | 

Optional

If `isAdditionalInfo` is set to `true`, then the **AdditionalInformation** field value of the bulk request is added to the outputMap.

 |

## Input JSON

Here's the sample input JSON when `isAdditionalInfo` is set to `false`:

```json
{      
    "requestId": "0rfxx000000001dAAA",
    "isAdditionalInfo": false
}
```

## Output JSON

Here's the sample output JSON when `isAdditionalInfo` is set to `false`:

```json
{
  "name": "Insurance_Enrollment",
  "createdDate": "Thu Nov 16 05:23:06 GMT 2023",
  "status": "Completed",
  'jobCount": 3,
  'pendingJobCount": 0,
  "successfulJobCount": 1,
  "failedJobCount": 2,
  "cancelledJobCount": 0,
  "erroredJobCount": 0,
  "requestItems" : [
  {
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
  }
  ]
 }
```

## Input JSON

Here's the sample input JSON when `isAdditionalInfo` is set to `true`:

```
{      
    "requestId": "0rfxx000000001dAAA",
    "isAdditionalInfo": true
 
}
```

## Output JSON

Here's the sample output JSON when `isAdditionalInfo` is set to `true`:

```json
{      
  "name": "Insurance_Enrollment",
  "createdDate": "Thu Nov 16 05:23:06 GMT 2023",
  "status": "Completed",
  'jobCount": 3,
  'pendingJobCount": 0,
  "successfulJobCount": 1,
  "failedJobCount": 2,
  "cancelledJobCount": 0,
  "erroredJobCount": 0,  
  "requestItems" : [
    {
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
    }
    ],
  "additionalInformation":{
                               "batchJobDetails":[{
                                    "batchJobId":"0mdxx0000000001AAA",  
                                    "productName":"prod1",                            
                                    "productId":"0rk1000000001dAAA"
                                                 }]
                            }
 
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo