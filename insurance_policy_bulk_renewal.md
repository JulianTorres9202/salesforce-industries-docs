---
title: "Insurance Policy Bulk Renewal Implementor Journey"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Bulk Renewal Implementor Journey

Insurance Policy Bulk Renewal Implementor Journey[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Bulk Renewal Implementor Journey

Automate the process of renewing multiple insurance policies at once with bulk renewal. Insurance providers can renew policies at scale by grouping eligible policies and processing them in batches.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform</td></tr></tbody></table>

Supported bulk policy renewal use cases:

-   Policy renewal without changes: Renews policies as is with repricing and rules evaluation.
-   Policy renewal with changes: Creates renewal quotes with repricing and rules evaluation.
-   Renewal Quotes: Adds, updates, or removes policy attributes and components before renewal.

-   **[Set Up Bulk Renewal](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal.htm&language=en_US&type=5)**  
    Configure the flow and batch job definitions for the bulk renewal process.
-   **[Schedule a Batch Job](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_schedule_flow.htm&language=en_US&type=5)**  
    Use a schedule-triggered flow to schedule your bulk policy renewal jobs to run automatically at a specified time and frequency. Make sure that each job run uses a unique identifier for easier monitoring of the policy renewal process. Schedule a custom Apex action by using the same approach.
-   **[Renew Policies with Changes](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_policy_renewal_with_changes.htm&language=en_US&type=5)**  
    Use an auto-launched flow to make changes to the policy before renewal. For bulk quote renewals, this flow is also recommended for updating additional fields, because copying additional fields by using fieldsets isn't supported.
-   **[Monitor Progress of Policy Renewals](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_monitoring.htm&language=en_US&type=5)**  
    Monitor the status of bulk policy or quote renewals and set up notifications by using entities, reports, and platform events.
-   **[Cancel a Bulk Renewal Job](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_cancellation.htm&language=en_US&type=5)**  
    Cancel bulk renewal jobs that are in progress to stop the enqueueing of additional policies. Policies that are already enqueued by the renewInsurancePolicies invocation action continue processing and can't be cancelled. When the job is completed, cancellation is no longer possible.
-   **[Best Practices for Bulk Policy Renewals](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_best_practices.htm&language=en_US&type=5)**  
    Learn best practices and avoid common issues to run bulk policy renewal jobs efficiently.
-   **[Troubleshoot Policy Renewal Failures](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renew_troubleshooting.htm&language=en_US&type=5)**  
    If some policy renewals fail because of errors, you can retry those policies by using a batch job or a custom action.

Did this article solve your issue?

Let us know so we can improve!

YesNo