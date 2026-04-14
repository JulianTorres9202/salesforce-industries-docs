---
title: "Best Practices for Bulk Policy Renewals"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_bulk_renewal_best_practices.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Best Practices for Bulk Policy Renewals

Best Practices for Bulk Policy Renewals[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Best Practices for Bulk Policy Renewals

Learn best practices and avoid common issues to run bulk policy renewal jobs efficiently.

Do's:

-   Validate all request-level input parameters before invoking the batch job. If any parameter is incorrect, all policies in the request fail with the same error, causing delays and failures.
-   Assign a unique job identifier for each batch job request to simplify the monitoring and tracking of different batch job requests.
-   If the batch request requires different inputs (for example, different PriceBooks based on product types), configure them in the batch job flow before invoking the renewInsurancePolicies action.
-   Make sure that any required custom fields for renewal quote creation are populated in the pre-step flow. These fields must have corresponding object mappings in the context definition.

Don'ts:

-   Don't change the effective start date and effective end date in the pre-processing flow. If they're changed in the context, these values aren't applied during renewal.
-   Because the batch process is single-threaded, keep the flow lightweight to avoid performance issues during bulk renewal execution.

Did this article solve your issue?

Let us know so we can improve!

YesNo