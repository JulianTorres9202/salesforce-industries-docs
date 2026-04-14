---
title: "InsContractService:createRenewQuotesInBatch"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createrenewquotesinbatch.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsContractService:createRenewQuotesInBatch

InsContractService:createRenewQuotesInBatch[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsContractService:createRenewQuotesInBatch

Use this service to allow you to control how many Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of contract renewals.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsContractService`

Method: `createRenewQuotesInBatch`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes a list of `contractIds`.
    
2.  The service breaks the list into the desired sub-list contracts and sends that to the renewal Integration Procedure (IP).
    
3.  The IP includes the steps for retrieving contract details, and calls the `createUpdateQuote` service for the creation of the renewal quote.
    
4.  The IP runs the processes within Salesforce limit (maximum five Apex jobs running in parallel).
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`contractIds`

 | 

Optional.

List of Contract Ids for renewal.

 |
| 

`renewalIPName`

 | 

Required.

Name of Integration Procedure to use for renewal of contracts.

 |
| 

`filters`

 | 

Filters used to identify contracts to be renewed.

Comma separated fieldName:fieldValue pair.

Example: `Status:Awaiting Approval`

This parameter can be supplied as either an option map or input map in the OmniScript.

 |
| 

`jobSize`

 | 

Number of contracts to be processed, per asynchronous Apex job.

This parameter determines how many Apex jobs are instantiated, given the number of contracts needed to renew.

IMPORTANT: Salesforce allows a maximum five Apex jobs to run in parallel.

 |
| 

`batchSize`

 | 

Number of contracts to be processed, per batch job.

This parameter determines how many batches to run, as per the number of contracts needed to process within one job.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output JSON below shows the `contractId` processed in each Apex job. This is helpful for debugging purposes.

```
{
 "apexJob2": [
  {
   "contractId": "8001J000000N0SGQA0"
  }
],
"apexJob1": [
  {
   "contractId": "8001J000000N0SGQA0"
  }
 ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo