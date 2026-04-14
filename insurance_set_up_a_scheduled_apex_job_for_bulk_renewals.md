---
title: "Set Up a Scheduled Apex Job for Bulk Renewals"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_a_scheduled_apex_job_for_bulk_renewals.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up a Scheduled Apex Job for Bulk Renewals

Set Up a Scheduled Apex Job for Bulk Renewals[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up a Scheduled Apex Job for Bulk Renewals

Create a job that references the RenewContractBatchJobScheduler Apex class and runs on a schedule that aligns with your renewal dates.

1.  From Setup, enter Apex Classes in the Quick Find box, select **Apex Classes**, then click **Schedule Apex**.
2.  Enter the following values:
    
    -   Job Name: <ADescriptiveJobName>
        
    -   Apex Class: RenewContractBatchJobScheduler
        
    -   Schedule Apex Execution: Enter a batch job schedule that makes sense based on the needs of your renewal dates.
        
    
3.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo