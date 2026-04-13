---
title: "Considerations and Limitations in Insurance Brokerage"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_known_issues.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Considerations and Limitations in Insurance Brokerage

Considerations and Limitations in Insurance Brokerage[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations and Limitations in Insurance Brokerage

Here are some considerations and limitations to keep in mind about Brokerage features.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

## Splits

[](https://help.salesforce.com/s?language=en_US)

-   The split arrangement search feature doesn't support special characters.
-   When using the Offset Duration in Producer Split Assignment, the end date for the first assignment and the effective date of second assignment is populated with a date that's one day later than it should be. The workaround is to update the date manually.
-   The dynamic enum values can’t be cleared once they're selected. The workaround is to delete thes row needs to be deleted.
-   In-bulk reassignment, only 50 records can be reassigned at once.

## Setup

[](https://help.salesforce.com/s?language=en_US)

-   The Insurance Rate Plan ID and Type fields can't be selected from Visible columns in Rate Plan Type Configuration.
-   The dynamic enum values can’t be cleared once they're selected.
-   Deleting empty rows in data table.
-   The API names need to be manually entered for Context Definition, Expression Set Definition, and Batch Process Job Definition for Insurance Policy Lifecycle Configuration, Policy Management, and Commission Processing repsectively.
-   On saving commission statement line item type configuration, if required field is not set,the error shows API names of the respective fields instead of labels.
-   Localization is not complete for all labels.

## Policy Lifecycle

[](https://help.salesforce.com/s?language=en_US)

-   The maximum number of entities in context definition is 50 and for the context persist API is 15 entities. Hence, customers can extend out-of-the-box context definition and add a maximum of 500 attributes, but can't add more than 15 entities.
-   The maimum number records in the insurance policy hierarchy is 1000.

## Commission Processing

[](https://help.salesforce.com/s?language=en_US)

-   The maximum number of batch jobs available is 5.
-   For the book of bsusiness split type, the Producer Allocation Amount field isn't visible as a related list.

Did this article solve your issue?

Let us know so we can improve!

YesNo