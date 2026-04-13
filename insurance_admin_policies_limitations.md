---
title: "Considerations and Limitations for Insurance Features"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policies_limitations.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Considerations and Limitations for Insurance Features

Considerations and Limitations for Insurance Features[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations and Limitations for Insurance Features

Review key limitations and usage considerations across core insurance features.

## Insurance Policy Administration

-   Policy Administration supports only single-root products and sequential endorsements.
-   The rating API always calculates the standard premium and standard tax amount on an annual basis, considering 365 days in a typical year and 366 days in a leap year.
-   You can't perform operations on canceled policies beyond the cancellation date.
-   You can't configure or customize the columns in the Policy Lightning Web Component to view policy details, but you can configure and customize the fields in the side panel.
-   The Status field population logic isn't supported out of the box, but it’s supported through additional fields.
-   You can pass additional fields (both standard and custom) as parameters and populate them in Insurance Policy, Insurance Policy Asset, Insurance Policy Coverage, and Insurance Policy Participant sObjects, but only through Insurance Policy Admin APIs and invocable actions.
-   Address and Geolocation data types aren't supported as additional fields.
-   All business logic considers only the date, compared to date + time in the package.
-   A policy in a different currency than the quote isn't supported.
-   There’s a limit of 1,000 quote line items, and a hard limit of 10,000 records per quote including necessary records such as attributes, relationship records, tax, and clauses.

## Quotes

-   Different quote line items in different currencies aren't supported.
-   A Quote Bundle can include up to 200 lines, including the root product. (This limit is planned to be increased in upcoming releases.)
-   Additional standard and custom fields can be passed as parameters and populated in the Quote and Quote Line Item sObjects exclusively through the Insurance Quoting API.
-   The maximum number of records that can be persisted in a single call to the Quoting API is 1,700, including Quote, Quote Line Item, Quote Line Item Related Objects, Quote Line Item Attributes, and other related objects.
-   Customers can create a quote without an opportunity by selecting a value in the Account For Quote field. To enable this feature, select Create Quotes Without a Related Opportunity in Quote Settings in Setup.
-   A Quote record can include a maximum of 1,000 quote line items and up to 8,000 quote line item attributes.

## General

Prioritize the use of pre-built Lightning Base Components to benefit from consistency, efficiency, performance, and security. Develop custom LWC components only when a unique requirement cannot be met by existing platform features.

Did this article solve your issue?

Let us know so we can improve!

YesNo