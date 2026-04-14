---
title: "New Sales"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_new_sales.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# New Sales

New Sales[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# New Sales

Use the New Sales Data Processing Engine template to get a list of new sales that are pending quote to policy conversion.

Here are the key nodes used in the New Sales Data Processing Engine template:

| Node Name | Node Type | Description |
| --- | --- | --- |
| Quotes | Data Source | The data source for quotes. |
| Status | Filter | Filters sourced quotes that are in Approved and Accepted status. |
| Days to Expire | Formula | Calculates the number of days between the quote expiration date and the current date. |
| Expiration Date | Filter | Filters quote based on the Days to Expire formula. |
| New Sales | Writeback Object | The dataset containing accepted or approved quotes that are expiring in 15 days. |

Did this article solve your issue?

Let us know so we can improve!

YesNo