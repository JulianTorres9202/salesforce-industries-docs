---
title: "Insurance Quoting APIs and Invocable Actions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_quoting_apis.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Insurance Quoting APIs and Invocable Actions

Insurance Quoting APIs and Invocable Actions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quoting APIs and Invocable Actions

Use quoting APIs to create, update, configure, and delete quotes and quote line items. Use the APIs to create guided flows for your external end users. Use invocable actions in Salesforce Flows and Omniscripts to gather information and create quotes.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions</td></tr></tbody></table>

## APIs

[](https://help.salesforce.com/s?language=en_US)

Insurance Create Quote API

This API performs a variety of functions, such as hydrate context, run rating processes, validate the product catalog, and run qualification and product configuration rules, and creates a quote.

Insurance Get Quote Detail API

This API fetches the details of a quote. It retrieves quote and quote line item details from a quote record, along with their attributes.

Insurance Update Quote API

This API performs key functions for existing quotes. It runs rating processes, validates the product catalog, and runs qualification and product configuration rules. It also adds and updates quote line item attributes, and deletes quote line items.

Insurance Product Rating API

This API rates products for use in quoting processes.

Insurance Product Surcharge API

This API calculates itemized taxes for quotes by using an expression set, amount, or percentage.

## Invocable Actions

[](https://help.salesforce.com/s?language=en_US)

Create Insurance Quote

This action creates an insurance quote by using a context ID or a set of user inputs that represent the quote details.

Get Insurance Quote Detail

This action fetches the details of an insurance quote.

Reprice Insurance Product

This action recalculates the price of insurance products based on user inputs.

#### See Also

-   [Insurance Quoting Connect APIs](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/quote_business_api_overview.htm)
-   [Insurance Quoting Invocable Actions](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/quote_invocable_actions_parent.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo