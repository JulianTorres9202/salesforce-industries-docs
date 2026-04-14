---
title: "Bulk Enroll Members"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_bulk_enroll_members.htm&language=en_US&type=5"
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

After you upload the group census data, click **Enroll**.

The `InsEnrollmentServiceStd:enrollMembersAsync` service creates policies for the group census members and calculates the employer contribution based on the group class specified for the primary members. To learn about the other tasks the service performs, see [InsEnrollmentServiceStd:enrollMembersAsync](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestdenrollmembersasync.htm&language=en_US&type=5 "Use this service to enroll large groups of members."). To learn about how the employer contribution is calculated for the created policies, see [Configure Data to Populate Employer Contribution in Policy Records](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_data_to_populate_employer_contribution_on_policy_records.htm&language=en_US&type=5 "Store employer contribution percentages and amounts in the policies created by the enrollment process.").

A message confirms that the enrollment request has been initiated and provides a request ID.

On the Insurance contract, the custom **Insurance Async Bulk Request** field shows the request ID link, and the **Enrollment Census** field shows the census ID of the census object with the uploaded members.

-   **[Bulk Enrollment Errors](https://help.salesforce.com/s/articleView?id=ind.insurance_common_bulk_enrollment_errors.htm&language=en_US&type=5)**  
    The most common errors in asynchronous census enrollment occur because of incorrect or incomplete input in the census. But flow configuration and exceptions can also cause asynchronous rating errors. The batch job status can help you locate where in the enrollment process an error happened.
-   **[Error Handling for Bulk Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_error_handling_bulk_enrollment.htm&language=en_US&type=5)**  
    During the bulk enrollment process, errors may occur during a CSV file upload or because of missing or inaccurate data processes by asynchronous enrollment job. Get notified when the enrollment is completed and receive a list of errors if enrollment couldn't be completed.

Did this article solve your issue?

Let us know so we can improve!

YesNo