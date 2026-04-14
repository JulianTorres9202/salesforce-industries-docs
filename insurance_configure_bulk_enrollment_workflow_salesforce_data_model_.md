---
title: "Configure the Bulk Enrollment Workflow for the Salesforce Data Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_bulk_enrollment_workflow_salesforce_data_model_.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Bulk Enrollment Workflow for the Salesforce Data Model

Configure the Bulk Enrollment Workflow for the Salesforce Data Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Bulk Enrollment Workflow for the Salesforce Data Model

Create a workflow that gives gives insurance carrier administrators a straightforward way to upload Group Benefits enrollment data for large groups with signed contracts.

`InsEnrollmentServiceStd:enrollMembers` runs the enrollment process synchronously and can enroll up to 200 members and two distinct plans.

The Enrollment Lightning web component works with the `InsEnrollmentServiceStd:enrollMembersAsync` service to support enrollment for large groups asynchronously. You can enroll up to 10,000 members and 30 distinct plans. With this service, the LWC also provides a way to handle errors that occur during enrollment.

-   **[Configure the Bulk Enrollment Census Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_bulk_enrollment_census_lightning_web_component.htm&language=en_US&type=5)**  
    The Enrollment Census Lightning web component gives insurance carrier administrators a straightforward way to upload census information with plan selection for Group Benefits Bulk Enrollment.
-   **[Download the Bulk Enrollment Configuration Solution](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_omniscript_error_handling_capability_bulk_enrollment.htm&language=en_US&type=5)**  
    Before you configure the OmniScript and error handling for bulk enrollment and new hire enrollment processes, download the custom solution that's available as a static resource.
-   **[Configure the Bulk Enrollment OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_bulk_enrollment_omniscript.htm&language=en_US&type=5)**  
    Customize the OmniScript that guides users through uploading census data for Group Benefits bulk enrollments and that creates the related objects in the Salesforce data model.
-   **[Set up Error Handling for Bulk Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_error_handling_capability_bulk_enrollment.htm&language=en_US&type=5)**  
    Get notified if any errors occur during a CSV file upload and when completed asynchronous jobs identify missing or incomplete data.
-   **[Create the Insurance Enrollment Batch Job for Asynchronous Bulk Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_enrollment_batch_job_asynchronous_enrollment_.htm&language=en_US&type=5)**  
    Create a batch job to process bulk enrollment requests asynchronously.
-   **[Configure Create Contacts Invocable Action](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_create_contacts_invocable_action.htm&language=en_US&type=5)**  
    Create matching rules and duplicate rules for the Contact object to avoid fuzzy matching and create contacts for the census members during bulk enrollment and new hire enrollment.
-   **[Configure the Salesforce Flow for Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_salesforce_flow_for_enrollment.htm&language=en_US&type=5)**  
    Use this flow to enroll group census members and create insurance policies based on their plan selection in the group census member plan.
-   **[Configure Data to Populate Employer Contribution in Policy Records](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_data_to_populate_employer_contribution_on_policy_records.htm&language=en_US&type=5)**  
    Store employer contribution percentages and amounts in the policies created by the enrollment process.

Did this article solve your issue?

Let us know so we can improve!

YesNo