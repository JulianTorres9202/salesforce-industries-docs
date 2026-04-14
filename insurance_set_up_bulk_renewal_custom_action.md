---
title: "Set Up Bulk Renewal by Using a Custom Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_bulk_renewal_custom_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Bulk Renewal by Using a Custom Action

Set Up Bulk Renewal by Using a Custom Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Bulk Renewal by Using a Custom Action

Use a custom Apex action to renew specific policies outside the bulk job flow.

Implement a custom Apex action that filters and selects policies for renewal, and call the out-of-the-box renewInsurancePolicies invocation action for each policy. This method works well for renewing a small number of policies or retrying policies that failed during the bulk renewal process. While the custom action handles specific renewals, the batch framework supports high-volume processing with built-in features for monitoring, fetching bulk data from the database, batching of requests, notifications, and troubleshooting.

Did this article solve your issue?

Let us know so we can improve!

YesNo