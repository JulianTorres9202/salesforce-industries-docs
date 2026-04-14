---
title: "InsContractService:createLargeSizeRenewQuoteInBatch"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservice__createlargesizerenewquoteinbatch.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsContractService:createLargeSizeRenewQuoteInBatch

InsContractService:createLargeSizeRenewQuoteInBatch[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsContractService:createLargeSizeRenewQuoteInBatch

Use this service to allow for the control of how many Apex jobs to initiate, and the number of batches to run per Apex job, for contracts with a large number of root line items.

The service breaks down contract line items by the `jobSize` and `batchSize` parameters and then calls the renewal Integration Procedure to generate a new quote.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsContractService`

[](https://help.salesforce.com/s?language=en_US)Method: `createLargeSizeRenewQuoteInBatch`

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`contractId`

 | 

Required.

Id of the large contract to be renewed.

 |
| 

`renewalIPName`

 | 

Required.

Name of the Integration Procedure that retrieves contract detail and creates the renewal quote.

 |
| 

`quoteName`

 | 

New name for renewal quote.

Default = contract name.

 |
| 

`jobSize`

 | 

Number of root contract line items, inside the contract, to be processed per asynchronous Apex job.

This parameter determines how many Apex jobs are instantiated, given the number of root contract line items inside the contract.

IMPORTANT: Salesforce allows a maximum five Apex jobs to run in parallel.

 |
| 

`batchSize`

 | 

Number of root contract line items to be processed, per batch job.

This parameter determines how many batches need to run, as per the given number of root line items needed to process within one job.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not require an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here is a sample output JSON where `jobSize` = 2.

```
{
"apexJob2": "[{"rootItemIds":["a0t1J00000GkwlYQAR"],"quoteId":"0Q01J000001D9GNSA0","contractId":"8001J000000MzMtQAK"}]",
"apexJob1": "[{"rootItemIds":["a0t1J00000GkwlWQAR"],"quoteId":"0Q01J000001D9GNSA0","contractId":"8001J000000MzMtQAK"},{"rootItemIds":["a0t1J00000GkwlXQAR"],"quoteId":"0Q01J000001D9GNSA0","contractId":"8001J000000MzMtQAK"}]"}  
```  

Did this article solve your issue?

Let us know so we can improve!

YesNo