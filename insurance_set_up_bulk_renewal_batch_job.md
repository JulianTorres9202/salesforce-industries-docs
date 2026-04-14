---
title: "Set Up Bulk Renewal by Using Industries Batch Job"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_batch_job.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Bulk Renewal by Using Industries Batch Job

Set Up Bulk Renewal by Using Industries Batch Job[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Bulk Renewal by Using Industries Batch Job

Set up a batch job that uses specific query criteria to identify eligible policies for renewal and to trigger the renewal process through a custom flow. The batch job definition must include a flow that runs for each policy record returned by the query. Call the renewInsurancePolicies invocable action within this flow to queue each policy for renewal. The renewInsurancePolicies invocable action is available out of the box, but you must manually create and configure the flow to use it. Schedule the batch job by using a schedule-triggered flow to run the renewal process at a specified time.

-   **[Create an Auto-Launched Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_auto_launched_flow.htm&language=en_US&type=5)**  
    Build a flow that receives input from the batch job and calls the renewInsurancePolicies invocation action for each policy record.
-   **[Create a Batch Job Definition](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_batch_job_definition.htm&language=en_US&type=5)**  
    Define a batch job that selects eligible insurance policies based on filter criteria and invokes a flow to process policies in bulk.

#### See Also

-   [Renew Insurance Policies Action](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/actions_obj_renew_insurance_policies.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo