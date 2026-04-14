---
title: "Lapsed Policies"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_lapsed_policies.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Lapsed Policies

Lapsed Policies[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Lapsed Policies

Use the Lapsed Policies Data Processing Engine template to get a list of lapsed insurance policies.

Here are the key nodes used in the Data Processing Engine template:

| Node Name | Node Type | Description |
| --- | --- | --- |
| Insurance Policies | Data Source | The data source for insurance policies. |
| Status | Filter | Filters insurance policies that are in Lapsed status. |
| Months Since Last Modification | Formula | Calculates the number of months since the insurance policy was last modified. |
| Last Modified Date | Filter | Filters insurance policies that are modified in the last 60 days. |
| Lapsed Policies | Writeback Object | The dataset containing the list of lapsed insurance policies. |

Did this article solve your issue?

Let us know so we can improve!

YesNo