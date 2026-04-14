---
title: "Customer Retention Offers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customer_retention_offers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customer Retention Offers

Customer Retention Offers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customer Retention Offers

Use the Customer Retention Offers Data Processing Engine Template to get a list of customers with active policies with fewer than 10 claims in the last 10 years.

The Customer Retention Offers Data Processing Engine template includes these key nodes:

| Node Name | Node Type | Description |
| --- | --- | --- |
| Insurance Policies | Data Source | The data source for insurance policies. |
| Claims | Data Source | The data source for claims. |
| Accounts | Data Source | The data source for accounts. |
| Claims Count | Filter | Filters accounts that have fewer than 10 claims. |
| Loss Date | Filter | Filters claims with the date in the last 10 years. |
| Expiration Date | Filter | Filters insurance policies based on the {formula name} formula. |
| Customer Retention Offers | Writeback Object | The dataset containing the list of low-risk customers. |
| Accounts with Claims and Policies | Join | Joins the claim details and insurance policy details with accounts. |
| Accounts and Policies | Join | Joins insurance policy details with accounts. |
| Claims and Policies | Join | Joins claim details with insurance policy details. |
| Months Since Loss Date | Formula | Calculates the number of months between the loss date and the current date. |
| Months Since Expiration Date | Formula | Calculates the number of months between the expiration date and the current date. |
| Customer Since | Formula | Calculates the number of years between the account creation date and the current date. |
| Claims Count | Formula | Calculates the total number of claims. |
| Claims Count and Total Claim Payout | Groups And Aggregate | Calculates the total claim payout and the total claim count. |
| Policies Count and Total Premium | Groups And Aggregate | The total number of policies and the premium amount for an account. |

Did this article solve your issue?

Let us know so we can improve!

YesNo