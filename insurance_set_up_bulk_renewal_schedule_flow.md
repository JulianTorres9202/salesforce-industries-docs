---
title: "Schedule a Batch Job"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_schedule_flow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Schedule a Batch Job

Schedule a Batch Job[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Schedule a Batch Job

Use a schedule-triggered flow to schedule your bulk policy renewal jobs to run automatically at a specified time and frequency. Make sure that each job run uses a unique identifier for easier monitoring of the policy renewal process. Schedule a custom Apex action by using the same approach.

1.  In Setup, find and select **Flows**.
2.  Click **New Flow**.
3.  Select **Schedule-Triggered Flow**.
4.  Set the start date, time, and frequency for the job.
5.  Create a formula resource to generate a unique jobIdentifier for each run.
    1.  Select **Formula** as the resource type.
    2.  Enter an API name.
    3.  Select **Text** as the data type.
    4.  Consider these strategies based on how frequently jobs are triggered.
        
        | Format | Description |
        | --- | --- |
        | PolicyRenewal\_<unixtimestamp> | Unique if only one job is created per second. |
        | PolicyRenewal\_<unixtimestamp>\_<last 4 chars of Flow.InterviewGuid> | Unique for multiple jobs created per second. |
        | PolicyRenewal\_<Flow.InterviewGuid> | Unique for all jobs. |
        
        The last four characters of Flow.InterviewGuid isn't often unique, so they must not be used as a standalone identifier.
        
    5.  Enter this formula.
        
        ```
        "PolicyRenewal_" & TEXT(UNIXTIMESTAMP(NOW())) & "_" & RIGHT({!$Flow.InterviewGuid}, 4)
        ```
        
        -   Length of unixtimestamp is 10 characters.
        -   Length of Flow.InterviewGuid is 43 characters.
        
6.  Add the Action element to your flow.
7.  In batch job actions, select your [batch job definition](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_batch_job_definition.htm&language=en_US&type=5 "Define a batch job that selects eligible insurance policies based on filter criteria and invokes a flow to process policies in bulk.").
    
    This batch job is used as an invocable action to be called when the scheduled flow runs.
    
8.  Pass all the required batch job parameters to this action, including a unique jobIdentifier.
9.  Save and activate the batch job.

#### See Also

-   [Schedule a Batch Job](https://help.salesforce.com/s/articleView?id=ind.task_schedule_batch_flow.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo