---
title: "Configure New Hire Enrollment and Termination Workflows for the Salesforce Data Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_new_hire_enrollment_termination_workflows_salesforce_data_model.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure New Hire Enrollment and Termination Workflows for the Salesforce Data Model

Configure New Hire Enrollment and Termination Workflows for the Salesforce Data Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure New Hire Enrollment and Termination Workflows for the Salesforce Data Model

The Mid-term Adjustments Lightning web component gives insurance carrier administrators a straightforward way to terminate group census members individually or in bulk asynchronously and enroll new hires in the middle of a contract term asynchronously.

## Add the Mid-Term Adjustments LWC to the Account Page

On a group Account page, from the Setup menu, click **Edit Page**. In the Lightning App Builder, add a custom tab, and then drag the **Mid-Term Adjustments** component into it.

## Input Parameters

Specify input parameters for the Mid-Term Adjustments Lightning web component properties.

| INPUT PROPERTY | PURPOSE |
| --- | --- |
| Bulk Termination CSV Template | The name of the template CSV file for bulk termination. |
| New Hire CSV Template | The name of the template CSV file for new hire enrollment. |
| Person Account Enabled | Specifies whether the user uses the Person Account flow for enrollment. |

-   **[Set Up New Hire Enrollment CSV Template](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_new_hire_enrollment_csv_template.htm&language=en_US&type=5)**  
    Use the New Hire Enrollment CSV template to enter the enrollment details for the new hire enrollment process.
-   **[Set Up the Bulk Termination CSV Template](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_termination_and_new_hire_enrollment_csv_templates.htm&language=en_US&type=5)**  
    The template stores details required for the bulk termination process.
-   **[Create the Insurance Enrollment Batch Job for Asynchronous New Hire Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_enrollment_batch_job_asynchronous_enrollment.htm&language=en_US&type=5)**  
    Create a batch job to process new hire enrollment requests asynchronously.
-   **[Configure the Salesforce Flow for New Hire Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_salesforce_flows_new_hire_enrollment.htm&language=en_US&type=5)**  
    The Enrollment flow compiles available products for group census members and process bulk enrollment.
-   **[Configure the OmniScript and Set Up Error Handling for New Hire Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_omniscript_set_up_error_handling_new_hire_enrollment.htm&language=en_US&type=5)**  
    Customize the OmniScript that walks users through uploading census data for Group Benefits new hire enrollments. Set up error handling to get notified if any errors occur during a CSV file upload and when completed asynchronous jobs identify missing or incomplete data
-   **[Configure the FlexCard to Launch New Hire Enrollment OmniScript on Group Account Page](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_flexcard_launch_omniscript_group_account_page.htm&language=en_US&type=5)**  
    After you configure the FlexCard to launch the New Hire Enrollment OmniScript on the Group Account page for the new hire enrollment process.

Did this article solve your issue?

Let us know so we can improve!

YesNo