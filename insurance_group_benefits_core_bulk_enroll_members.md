---
title: "Bulk Enroll Members"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_bulk_enroll_members.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Bulk Enroll Members

Bulk Enroll Members[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Bulk Enroll Members

You can bulk enroll up to 10,000 census members into their selected plans and policies.

### Required Editions

After you upload the group census data, click **Enroll**.

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

The Insurance Group Enrollment API creates policies for the group census members and calculates the employer contribution based on the group class specified for the primary members. To learn about the other tasks the API performs, see Group Enrollment API. To learn about how the employee and employer contribution is calculated for the created policies, see [Configure Group Class Contribution](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_group_class_configure.htm&language=en_US&type=5 "Create one or more group class contribution records for each of the associated group classes with the account based on the plan or coverage information.").

-   **[Bulk Enrollment Errors](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_bulk_enrollment_errors.htm&language=en_US&type=5)**  
    The most common errors in asynchronous census enrollment occur because of incorrect or incomplete input in the census. But flow configuration and exceptions can also cause asynchronous rating errors. The batch job status can help you locate where in the enrollment process an error happened.
-   **[Error Handling for Bulk Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_enrollment_error_handle.htm&language=en_US&type=5)**  
    During the bulk enrollment process, errors may occur during a CSV file upload or because of missing or inaccurate data processes by asynchronous enrollment job. Get notified when the enrollment is completed and receive a list of errors if enrollment couldn't be completed.

Did this article solve your issue?

Let us know so we can improve!

YesNo