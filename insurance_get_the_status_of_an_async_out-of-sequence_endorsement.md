---
title: "Get the Status of an Async Out-of-Sequence Endorsement"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_get_the_status_of_an_async_out-of-sequence_endorsement.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Get the Status of an Async Out-of-Sequence Endorsement

Get the Status of an Async Out-of-Sequence Endorsement[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Get the Status of an Async Out-of-Sequence Endorsement

Use InsPolicyService:getOutOfSequenceEndorsementStatus to retrieve the current status of an out-of-sequence-endorsement async job.

Here are the possible status values:

| Async Job Status | What It Indicates |
| --- | --- |
| WaitingToProcess | The job is in the queue. |
| InProgress | The job is in progress. |
| Success | The endorsement is completed and new policy versions are created. |
| Failed | The endorsement failed. |
| Aborted | The admin stopped the job. |

The most common errors in asynchronous out-of-sequence endorsement processes occur because of issues with the Apex job. Reviewing the async job status can help you determine if the endorsement failed or the admin stopped the async job. You can then connect with the administrator to learn the details.

Did this article solve your issue?

Let us know so we can improve!

YesNo