---
title: "Life Event Updates"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_life_event_updates.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Life Event Updates

Life Event Updates[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Life Event Updates

Use the Life Event Updates Data Processing Engine Template to get a list of customer life event updates for the last three months.

The Life Event Updates Data Processing Engine template includes these key nodes:

| Node Name | Node Type | Description |
| --- | --- | --- |
| Insurance Policies | Data Source | The data source for insurance policies. |
| Life Events | Data Source | The data source for life events. |
| Accounts | Data Source | The data source for accounts. |
| Event Date | Filter | Filters events that are older than three months. |
| Life Event Updates | Writeback Object | The dataset containing the list of life events from the last three months. |
| Accounts with Events and Policies | Join | Joins the account details for policies and events. |
| Accounts and Policies | Join | Joins insurance policies' details with accounts. |
| Dependents and Properties | Join | Adds number of assets and dependents to the dataset. |
| Months Since Event | Formula | Calculates the number of months between the creation date and the current date. |
| Total Premium | Groups And Aggregate | Calculates the total premium amount received from an account. |

Did this article solve your issue?

Let us know so we can improve!

YesNo