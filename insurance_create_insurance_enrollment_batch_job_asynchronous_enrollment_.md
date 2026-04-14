---
title: "Create the Insurance Enrollment Batch Job for Asynchronous Bulk Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_enrollment_batch_job_asynchronous_enrollment_.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create the Insurance Enrollment Batch Job for Asynchronous Bulk Enrollment

Create the Insurance Enrollment Batch Job for Asynchronous Bulk Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create the Insurance Enrollment Batch Job for Asynchronous Bulk Enrollment

Create a batch job to process bulk enrollment requests asynchronously.

To create batch jobs, users must have the `BatchManagementAddOn` license.

1.  From Setup, in the Quick Find box, enter Batch Management, and then select **Batch Management**.
2.  Click **New**.
3.  In the New batch job, enter these values:
    
    | Field | Value |
    | --- | --- |
    | **Name** | Insurance Enrollment |
    | **API Name** | Insurance \_Enrollment |
    | **Description** | For LG ENrollment Process |
    | **Process Type** | Flow |
    | **Execution Process** | Enrollment Flow |
    | **Group** | Group 1 |
    | **Batch Size** | 50 |
    | **Retry Count** | 1 |
    | **Retry Interval** | 1000 |
    
4.  Click **Next**, and then enter these values:
    
    | Field | Value |
    | --- | --- |
    | **Flow Input Variable** | groupCensusMemberId |
    | **Object** | Group Census Member |
    | **Conditions** | **All Conditions Are Met (AND)** |
    | **Resource**: Group Census ID | **Operator**: Equals | **Type**: Input Variable | **Value**: groupCensusId |
    | **Resource**: Relationship to Primary Member | **Operator**: Equals | **Type**: Value | **Value**: Self |
    
5.  Click **Save**, and then **Activate**.

Did this article solve your issue?

Let us know so we can improve!

YesNo