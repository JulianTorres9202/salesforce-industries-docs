---
title: "Bulk Enrollment Errors"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_common_bulk_enrollment_errors.htm&language=en_US&type=5"
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

## Common Bulk Enrollment Errors

The most common errors in asynchronous census enrollment occur because of incorrect or incomplete input in the census. But flow configuration and exceptions can also cause asynchronous rating errors. The batch job status can help you locate where in the enrollment process an error happened.

| Batch Job Status | Where the Error Happened |
| --- | --- |
| Completed with errors | Enrollment flow |
| Completed | Enrollment flow completed |
| Failed | Failed to schedule the job due to non-availability of jobs |

## Business-specific Enrollment Errors

During enrollment, you may encounter errors that occur when certain business logic is not met.

| Feature Name | Usage | Error Message | Batch Job Status | Note |
| --- | --- | --- | --- | --- |
| Duplicate Policy Check | If an active policy already exists for a member, avoid creating another policy for the same member within the same plan category. | We couldn’t create policy records for these members because the members are already enrolled: {member names}. | A policy already exists for the member {member name} in the category {category name} with the policy number {policy number}. | Ensure to run `InsContractServiceStd.createUpdateContract` service on existing active contracts without changing any information. |

Did this article solve your issue?

Let us know so we can improve!

YesNo