---
title: "InsPolicyService:getPolicyAsyncJobStatus"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getpolicyasyncjobstatus.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getPolicyAsyncJobStatus

InsPolicyService:getPolicyAsyncJobStatus[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getPolicyAsyncJobStatus

Use this service to fetch the status of the asynchronous batch job.

Class: `InsPolicyService`

Method: `getPolicyAsyncJobStatus`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

[](https://help.salesforce.com/s?language=en_US)

1.  The service takes `jobId`, `policyId`, or `referencePolicyNumber` as an input parameter. When you pass more than one input parameter in the request, the `jobId` takes precedence, followed by `policyId`, and then `referencePolicyNumber`.
    
    [](https://help.salesforce.com/s?language=en_US)Important If you pass more than one of the accepted parameters and any one of them is invalid, the service returns an error.
    
2.  The service first validates field-level permissions and then retrieves the status of the asynchronous process. The possible values are:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   `WaitingToProcess`—The job is in the queue.
        
    -   `InProgress`—The job is in progress.
        
    -   `Success`—The job is successful.
        
    -   `Failed`—The job failed.
        
    -   `Aborted`—The admin aborted the operation.
        
3.  The service returns the status of the latest `jobId` for a given policy based on the `createdDate`.
    

[](https://help.salesforce.com/s?language=en_US)

## Inputs

You must pass one of these inputs.

| Input | Description |
| --- | --- |
| `jobId` | 
The asynchronous job ID that’s returned by the asynchronous batch job.

 |
| `policyId` | 

The policy ID being monitored by the asynchronous job.

 |
| `referencePolicyNumber` | 

The reference number of the policy. This option isn’t supported for multi-root services.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the sample input JSON.

[](https://help.salesforce.com/s?language=en_US)`{      "jobId": "7075j00004uK6GjAAK"               or      "policyId": "0YT5w000000Y8MNGA0"               or      "referencePolicyNumber": "0YT5w000000Y8MNGA0" }`
  

[](https://help.salesforce.com/s?language=en_US)

## Output

| Option | Description |
| --- | --- |
| `jobId` | The asynchronous job ID for the process. If you didn't provide the `jobId` as input and must know it, you can retrieve it from the output. |
| `status` | The status of the asynchronous process. Possible values include: WaitingToProcess, InProgress, Success, Failed, and Aborted. |
| `error` | The error message that’s returned when a job succeeds, fails, or is aborted. |

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the sample output JSON.

[](https://help.salesforce.com/s?language=en_US)`{       "status": "Success",       "jobId": "7075j00004uK6GjAAK",       "errorCode": "INVOKE-200",       "error": "OK" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo