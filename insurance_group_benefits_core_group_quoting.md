---
title: "Group Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_group_quoting.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Quoting

Group Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Quoting

Quickly and efficiently configure, reprice, and view group quotes to help your customers provide their employees with exactly the coverage they need. Group quoting is supported for member-based and summary-based quotes.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

Note By default, admins create group quotes from opportunities. If your business process doesn’t use opportunities, enable the setting to create quotes directly. [Learn more about creating quotes without opportunities](https://help.salesforce.com/s/articleView?id=sales.cpq_quotes_without_opportunities.htm&language=en_US&type=5).

Considerations and validations for adding a group quote:

-   Insurance Quote Type must be set to New Group Business.
-   Group census must be linked to the quote.
-   Quote account must match the census account.
-   Quote start and end dates must fall within the census effective and expiration dates.
-   Use the Insurance Quote Line Item Grid Lightning Web Component (LWC) to:
    -   View and manage quote line items in a hierarchy.
    -   Perform row-level actions such as Rate and Configure.
    -   Rate a quote.
    -   Open the side panel to view product, pricing, and attribute details.

-   **[Set Up Product Configuration Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_set_up_product_configuration_flow.htm&language=en_US&type=5)**  
    Before you configure products on a group quote, set up a product configuration flow for the Group Summary product classification. The flow automatically loads group census group class records into the configurator and so that users don’t have to add group classes and members manually.
-   **[Add and Configure Products on a Group Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_add_and_configure_group_quote.htm&language=en_US&type=5)**  
    Use the configurator to add a root product to a group quote and configure its group classes, members, and coverages.
-   **[Rate a Group Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_rate_group_quote.htm&language=en_US&type=5)**  
    Use rating to calculate premiums for group quotes based on census data, plan selection, and pricing procedures. Rating runs either at the member level or the group summary level depending on the value selected in the Census Rating Type field on the quote.

Did this article solve your issue?

Let us know so we can improve!

YesNo