---
title: "InsPolicyService:renewPoliciesInBatch"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__renewpoliciesinbatch.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:renewPoliciesInBatch

InsPolicyService:renewPoliciesInBatch[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:renewPoliciesInBatch

Use this service to control the number of Apex jobs to initiate, and the number of batches to run per Apex job, for a large number of policy renewals.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

[](https://help.salesforce.com/s?language=en_US)Method: `renewPoliciesInBatch`

[](https://help.salesforce.com/s?language=en_US)

## How it Works

This service initiates multiple Apex jobs and each job renews the policies in batches by invoking `createRenewalPolicy` service internally.

1.  The service takes a list of `policyIds`.
    
2.  The service breaks the list into the desired sub-list policies and sends those to the `createRenewalPolicy` service for creation of renewal policies.
    

Note To understand the limitations and what isn't supported, see [Considerations and Limitations for Insurance Policies](https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_limitations_for_insurance_policies.htm&language=en_US&type=5 "Here are some things to keep in mind about Insurance Policies.").

[](https://help.salesforce.com/s?language=en_US)

## Inputs

| 
Input

 | 

Description

 |
| --- | --- |
| 

`policyId`

 | 

The ID of the policy that is to be renewed.

 |

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Remote Option

 | 

Description

 |
| --- | --- |
| 

`renewalClassName`

 | 

The service class name (`InsPolicyService.createRenewalPolicy`) for creation of renewal policies.

 |
| 

`jobSize`

 | 

Number of policies to be renewed, per asynchronous Apex job.

This parameter determines how many Apex jobs are instantiated, given the number of policies to be renewed.

Important

Salesforce allows a maximum five Apex jobs to run in parallel.







 |
| 

`batchSize`

 | 

Number of policies to be renewed, per batch job.

This parameter determines how many batches to run, as per the number of policies needed to process within one job.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's an example of the input JSON:

```json
"policyIds": [
     "0YT5w000000Y8MNGA0",
     "0YT5w000000Y8MIGA0",
     "0YT5w000000Y8MDGA0",
     "0YT5w000000Y8M8GAK"
   ]
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

There's no output JSON for this service.

Did this article solve your issue?

Let us know so we can improve!

YesNo