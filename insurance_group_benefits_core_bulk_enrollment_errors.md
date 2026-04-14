---
title: "Bulk Enrollment Errors"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_bulk_enrollment_errors.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Bulk Enrollment Errors

Bulk Enrollment Errors[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Bulk Enrollment Errors

The most common errors in asynchronous census enrollment occur because of incorrect or incomplete input in the census. But flow configuration and exceptions can also cause asynchronous rating errors. The batch job status can help you locate where in the enrollment process an error happened.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

## Common Bulk Enrollment Errors

The most common errors in asynchronous census enrollment occur because of incorrect or incomplete input in the census. But flow configuration and exceptions can also cause asynchronous rating errors. The batch job status can help you locate where in the enrollment process an error happened.

| Batch Job Status | Where the Error Happened |
| --- | --- |
| Completed with errors | Enrollment flow |
| Completed | Enrollment flow completed |
| Failed | Failed to schedule the job due to non-availability of jobs |

## Business-specific Enrollment Errors

During enrollment, you may encounter errors that occur when certain business logic is not met.

| Feature Name | Usage | Error Message | Batch Job Status |
| --- | --- | --- | --- |
| Duplicate Policy Check | If an active policy already exists for a member, avoid creating another policy for the same member within the same plan category. | We couldn’t create policy records for these members because the members are already enrolled: {member names}. | A policy already exists for the member {member name} in the category {category name} with the policy number {policy number}. |

Note This error appears only if the Is Duplicate Check field is set to True in the Process Member Enrollment action.

Did this article solve your issue?

Let us know so we can improve!

YesNo