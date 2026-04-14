---
title: "Error Handling for Bulk Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_enrollment_error_handle.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Error Handling for Bulk Enrollment

Error Handling for Bulk Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Error Handling for Bulk Enrollment

During the bulk enrollment process, errors may occur during a CSV file upload or because of missing or inaccurate data processes by asynchronous enrollment job. Get notified when the enrollment is completed and receive a list of errors if enrollment couldn't be completed.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

## Errors During a CSV File Upload

If the uploaded CSV file contains data errors, you receive an error message. In the downloaded CSV file, review and correct the errors. If you skip this step, members with errors aren't enrolled.

After you fix the errors, upload the CSV file again, and then click **Enroll**.

## Errors After Asynchronous Jobs are Completed

Quickly generate and view a list of enrollment request errors for large groups with the click of a button.

After an enrollment request completes with errors, you’ll be notified through a notification. Click the notification message under the Notifications icon. A CSV file summarizing the errors is created and attached to the Group Census page in the Files related list.

The CSV file name format (AccountName)\_ + (InsuranceEnrollmentRequestId)\_ + (CSV generation time) helps users locate and correct issues more easily. The file name uniquely identifies the account and enrollment request associated with the errors.

Fix the errors in the CSV file. Upload the file again and click **Enroll**. The other way to fix the errors is to click the action menu for the member with errors to fix, and then select **Edit Member**. Make necessary changes to fix the errors, and then click **Enroll**.

Did this article solve your issue?

Let us know so we can improve!

YesNo