---
title: "High-Value Customers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_high_value_customers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# High-Value Customers

High-Value Customers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# High-Value Customers

Use High-Value Customers Data Processing Engine Template to get a list of accounts with a total premium that's more than $100,000 a year.

The High-Value Customers Data Processing Engine template includes these key nodes:

| Node Name | Node Type | Description |
| --- | --- | --- |
| Insurance Policies | Data Source | The data source for insurance policies. |
| Claims | Data Source | The data source for claims. |
| Accounts | Data Source | The data source for accounts. |
| Total Premium | Filter | Filters accounts with a total premium that's less than $100,000. |
| High-Value Customers | Writeback Object | The dataset containing the list of high-value accounts. |
| Accounts and Policies | Join | Joins insurance policies with accounts. |
| Accounts with Claims and Policies | Join | Joins insurance policies and claims with accounts. |
| Dependents and Properties | Join | Adds number of assets and dependents to the dataset. |
| Claims and Policies | Join | Joins claim details with insurance policy details. |
| Customer Since | Formula | Calculates the number of years between the account creation date and the current date. |
| Total Claim Payout and Claim Count | Groups And Aggregate | Calculates the total claim payout and the total claim count. |
| Total Premium | Groups And Aggregate | The total premium amount received from an account. |

Did this article solve your issue?

Let us know so we can improve!

YesNo