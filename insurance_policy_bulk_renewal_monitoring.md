---
title: "Monitor Progress of Policy Renewals"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_monitoring.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Monitor Progress of Policy Renewals

Monitor Progress of Policy Renewals[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Monitor Progress of Policy Renewals

Monitor the status of bulk policy or quote renewals and set up notifications by using entities, reports, and platform events.

## Entities for Monitoring Bulk Renewal Status

Create Custom Report Types (CRTs) to track the status of bulk renewal jobs based on these monitoring entities.

InsuranceAsyncBulkRequest

This is the master entity that stores the jobIdentifier passed to the renewInsurancePolicies invocable action via the batch job. A record is created for each unique jobIdentifier.

InsuranceAsyncBulkRecordDetail

This entity has a foreign key relationship with the InsuranceAsyncBulkRequest entity. It tracks the execution status of each individual policy renewal request. A record is created in the Scheduled status when the renewInsurancePolicies invocable action is triggered, indicating that the renewal request was received for that policy. The status transitions to In Progress when the policy is placed in the message queue for processing. The final status is Success or Failure, depending on the outcome of the renewal process. The additionalInformation field stores error details if the renewal fails and populates renewed record ID (policyId or quoteId), if the renewal succeeds.

## Custom Report Type (CRT) for Monitoring Bulk Renewals

Use CRTs to check the real-time status of your bulk renewal requests. CRT is enabled on the monitoring entities InsuranceAsyncBulkRequest and InsuranceAsyncBulkRecordDetail, so you can easily build reports on renewal activity. In Report Builder, create a report for a specific bulk renewal request, filter it using the jobIdentifier field, and group the results by status. To avoid manually running or emailing reports, subscribe to the report. You can set conditions so that team members receive a notification when certain values in the report meet a specific threshold.

## Event-Based Notifications Per Policy or Quote Renewal

You receive notifications after each policy or quote is renewed as part of a bulk request. These notifications help you perform any follow-up actions for each renewed policy or quote, whether the renewal succeeds or fails. Two types of events are triggered:

InsPolicyRnwlStatusEvent

This event is triggered after each policy renewal. It includes the source policy ID, renewed policy ID (if successful), the status (Success or Failure), and the jobIdentifier that links the renewal to the correct job.

InsPolicyRnwlQuoteStatusEvent

This event is triggered after each quote renewal. It includes the source policy ID, renewed quote ID (if successful), the status, and the jobIdentifier for the request.

## End-of-Job Notification for Bulk Renewal

Sending notifications at the end of a bulk renewal job isn’t supported out of the box. However, you can still set up notifications in these ways.

-   Subscribe to reports to receive updates when specific conditions are met, without running the reports manually. See [Schedule and Subscribe to Reports](https://help.salesforce.com/s/articleView?id=analytics.reports_subscribe_overview.htm&language=en_US&type=5).
-   Use a platform event triggered by the batch framework at the end of the job. A Platform Event–Triggered flow can listen for Batch Job Status Change Events to notify you when the job is completed. See [Set Up Process End Notification for Bulk Renewals](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_monitor_completion.htm&language=en_US&type=5 "Learn how to use the platform event from the batch framework to detect when a bulk policy renewal job completes and trigger a notification or follow-up action. Use the platform event triggered by the batch framework at the end of a batch job. A Platform Event–Triggered flow subscribes to all Batch Job Status Change Events from the batch framework.").

-   **[Set Up Process End Notification for Bulk Renewals](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_monitor_completion.htm&language=en_US&type=5)**  
    Learn how to use the platform event from the batch framework to detect when a bulk policy renewal job completes and trigger a notification or follow-up action. Use the platform event triggered by the batch framework at the end of a batch job. A Platform Event–Triggered flow subscribes to all Batch Job Status Change Events from the batch framework.

Did this article solve your issue?

Let us know so we can improve!

YesNo