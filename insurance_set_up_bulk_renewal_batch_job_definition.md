---
title: "Create a Batch Job Definition"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_batch_job_definition.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Batch Job Definition

Create a Batch Job Definition[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Batch Job Definition

Define a batch job that selects eligible insurance policies based on filter criteria and invokes a flow to process policies in bulk.

1.  In Setup, find and select **Batch Management**.
2.  Click **New**.
3.  Provide these details.
    1.  Specify a name of the batch job.
    2.  Select **Flow** as the process type.
    3.  In Execution Process, select the auto-launched flow that you created for policy renewal.
    4.  Enter the batch size, up to 2,000 records.
    5.  Enter the retry count.
        
        Set the retry count with caution. If the renewInsurancePolicies invocable action runs successfully but the flow fails later, the policy is still renewed because it's already enqueued. Retrying can result in duplicate renewals.
        
    6.  In Retry Interval, enter the time (in milliseconds) to wait before running the failed batch job again.
4.  Click **Next**.
5.  In Flow Input Variable, specify the text variable to accept the Policy ID.
6.  Select **Insurance Policy** as the object.
7.  Set the filter conditions to return unique and valid policy records for renewal.
8.  Save your changes, and activate the batch job.

#### See Also

-   [Create a Batch Job](https://help.salesforce.com/s/articleView?id=ind.task_create_batch_job.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo