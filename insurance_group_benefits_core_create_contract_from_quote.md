---
title: "Create a Contract from a Quote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_contract_from_quote.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Contract from a Quote

Create a Contract from a Quote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Contract from a Quote

After you approve a group quote and the customer agrees to purchase coverage, create a contract from the quote.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create a contract | Digital Insurance Group Census Quote Contract Management, Digital Insurance Group Census Quote Contract Management Partner Community |

Before you create contract, ensure that you add at least one of Account or Account for Quote to the quote. The contract defines the agreement between the insurance carrier and the group.

To create a contract, use the Create Contract from Quote API or build a screen flow that runs the Create Contract from Quote using Create Contract invocable action. You will be notified through a notification message confirming the creation of contract and related records.

Note If you invoke this action from a flow, make sure to select **Manually assign variables (advanced)** when mapping outputs. The output field asyncBulkRequestId isn’t supported with the flow’s automatic variable mapping. If this option is left unchecked, the flow fails with an error.

Did this article solve your issue?

Let us know so we can improve!

YesNo