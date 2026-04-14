---
title: "Policy Renewals"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_renewals.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Policy Renewals

Policy Renewals[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Policy Renewals

Use the Policy Renewals Data Processing Engine template to get a list of insurance policies that are up for renewal in the next 30 days.

Here are the key nodes used in the Data Processing Engine template:

| Node Name | Node Type | Description |
| --- | --- | --- |
| Insurance Policies | Data Source | The data source for insurance policies. |
| Status | Filter | Filters insurance policies that are in In Force and Unrenewed status. |
| Months before Renewal | Formula | Calculates the number of months between the policy renewal date and the current date. |
| Renewal Date | Filter | Filters the insurance policies that are expiring in the next 30 days. |
| Policy Renewals | Writeback Object | The dataset containing in-force and unrenewed insurance policies that are up for renewal in the next 15 days. |

Did this article solve your issue?

Let us know so we can improve!

YesNo