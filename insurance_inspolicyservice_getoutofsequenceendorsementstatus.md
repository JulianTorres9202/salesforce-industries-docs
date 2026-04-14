---
title: "InsPolicyService:getOutOfSequenceEndorsementStatus"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getoutofsequenceendorsementstatus.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:getOutOfSequenceEndorsementStatus

InsPolicyService:getOutOfSequenceEndorsementStatus[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:getOutOfSequenceEndorsementStatus

Use this service to retrieve the current status of the OutOfSequenceEndorsement async job. The service accepts jobId, policyId, or referencePolicyNumber as an input to fetch the out-of-sequence endorsement operation status.

Class: `InsPolicyService`

Method: `getOutOfSequenceEndorsementStatus`

## How It Works

1.  The service takes `jobId` or `policyId` or `referencePolicyNumber` as an input parameter. When you pass more than one input parameters in the request, the `jobId` takes precedence, then `policyId` and then `referencePolicyNumber`.
    
    Important If you pass more than one of the accepted parameters and any one of them is invalid, the service returns an error.
    
2.  The service retrieves the current status of the `OutOfSequenceEndorsement` process. The possible values are:
    
    -   `WaitingToProcess` - The job is in the queue.
        
    -   `InProgress` - The endorsement is in progress.
        
    -   `Success` - The endorsement is successful and new policy versions are created.
        
    -   `Failed` - The endorsement failed.
        
    -   `Aborted` - The admin aborted the operation.
        
3.  The service returns the status of latest `jobId` for a given policy based on the `createdDate`. For example, if a policy has more than two out-of-sequence endorsed in a period, the status of the last out-of-sequence endorsement is returned.
    

## Inputs

You must pass one of these inputs:

| Input | Description |
| --- | --- |
| `jobId` | The async job ID that's returned by OutOfSequenceEndorsement job. |
| `policyId` | The policyId of the latest policy version that's endorsed. |
| `referencePolicyNumber` | The reference policy number of the endorsed policy. |

## Input JSON

Here's the sample input JSON:

```json
{
   "jobId": "7075j00004uK6GjAAK"
     
    or
 
   "policyId": "0YT5w000000Y8MNGA0"
 
    or
 
    "referencePolicyNumber" "0YT5w000000Y8MNGA0"
}   
```

## Output

| Option | Description |
| --- | --- |
| `jobId` | The async job ID for the OutOfSequenceEndorsement process. If you didn't pass a `jobId` as input and want to know what it is, you can get it from the output. |
| `status` | The status of the outOfSequenceEndorsement process. Possible values are: WaitingToProcess, InProgress, Success, Failed, Aborted. |
| `error` | The error message that's returned when a job fails. |

## Output JSON

Here's the sample output JSON:

```json
{
      "status": "Success",
      "jobId": "7075j00004uK6GjAAK",
      "errorCode": "INVOKE-200",
      "error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo