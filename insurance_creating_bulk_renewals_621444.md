---
title: "Creating Bulk Renewals"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_creating_bulk_renewals_621444.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Creating Bulk Renewals

Creating Bulk Renewals[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Creating Bulk Renewals

The renewal business process begins once a customer (individual or group) is sold. But plan designs often change, so renewals must take into account when benefit plans are retired and what new plans take their place.

[](https://help.salesforce.com/s?language=en_US)

Renewal management is the art and science of creating new renewal packages, which include opportunities, quotes, and quote line items. Renewal packages come from the previous year’s contracted benefits, which consist of contract and contract lines items (plans), before a customer’s renewal date. Renewal dates are usually 90 days before the in-force plan expires.

[](https://help.salesforce.com/s?language=en_US)

Renewals happen throughout the year, with certain peak months requiring most of the work. Some renewals require approvals from underwriters before they can be seen by brokers and customers. Customers are usually notified of their new plans 30-60 days prior to their new plan's effective date. Customers and their brokers can then view and decide to keep the renewal plan or not. Customers can accept the plan as-is, add to it with new benefits, or shop for alternative plans.

[](https://help.salesforce.com/s?language=en_US)

You can save time by creating renewals in bulk.

1.  [Set Up a Scheduled Apex Job for Bulk Renewals](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_a_scheduled_apex_job_for_bulk_renewals.htm&language=en_US&type=5 "Create a job that references the RenewContractBatchJobScheduler Apex class and runs on a schedule that aligns with your renewal dates.")
    
    Create a job that references the RenewContractBatchJobScheduler Apex class and runs on a schedule that aligns with your renewal dates.
    
2.  [Configure Custom Settings for Bulk Renewals](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_bulk_renewals_621444.htm&language=en_US&type=5#insurance_creating_bulk_renewals_621444__section_7015b62bf20e0c2a0281fcf3bc998a4e)
    
    You need to configure two custom settings to make batch renewal generation work: RenewContractBatchJobProcess and RenewContractBatchJobQuery.
    
3.  [Tag Contracts for Renewal](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_bulk_renewals_621444.htm&language=en_US&type=5#insurance_creating_bulk_renewals_621444__section_c5232756cf9912b7415a4563b4768dd6)
    
    Tag contracts up for renewal so that your scheduled Apex job can renew them in bulk.
    

[](https://help.salesforce.com/s?language=en_US)

## Configure Custom Settings for Bulk Renewals

You need to configure two custom settings to make batch renewal generation work: RenewContractBatchJobProcess and RenewContractBatchJobQuery.

1.  From Setup, enter Custom Settings in the Quick Find box, then click **Custom Setting**.
    
2.  Next to Custom Class Implementation, click **Manage**, then click **New**.
    
3.  Enter the following values:
    
    -   Name: RenewContractBatchJobProcess
        
    -   Class Name: HealthInsuranceContractRenewalProcess
        
4.  Click **Save & New**.
    
5.  Enter the following values:
    
    -   Name: RenewContractBatchJobQuery
        
    -   Class Name: HealthInsuranceContractRenewalQuery
        

[](https://help.salesforce.com/s?language=en_US)

## Tag Contracts for Renewal

Tag contracts up for renewal so that your scheduled Apex job can renew them in bulk.

Note

The Contract Name field cannot be empty on any contract that's tagged for automatic batch renewal generation.

1.  On the Contracts page, choose **All Contracts** in the list view dropdown.
    
2.  Check all the contracts you want to renew.
    
3.  Click **Tag for Renewal** at the top right of the page.
    

When the scheduled Apex job executes, the renewals that correspond to the selected contracts are created. To see them, go to the Opportunities page and choose the All Renewals view.

-   **[Set Up a Scheduled Apex Job for Bulk Renewals](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_a_scheduled_apex_job_for_bulk_renewals.htm&language=en_US&type=5)**  
    Create a job that references the RenewContractBatchJobScheduler Apex class and runs on a schedule that aligns with your renewal dates.

Did this article solve your issue?

Let us know so we can improve!

YesNo