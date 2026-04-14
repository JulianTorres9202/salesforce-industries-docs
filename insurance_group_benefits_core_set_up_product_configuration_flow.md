---
title: "Set Up Product Configuration Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_set_up_product_configuration_flow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Product Configuration Flow

Set Up Product Configuration Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Product Configuration Flow

Before you configure products on a group quote, set up a product configuration flow for the Group Summary product classification. The flow automatically loads group census group class records into the configurator and so that users don’t have to add group classes and members manually.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To set up a product configuration flow: | Digital Insurance Group Census Quote Contract Management, Digital Insurance Group Census Quote Contract Management Partner Community |

A pre-built CnfgGrpSum flow is available out-of-the-box. This flow displays the list of group census group class summary records linked to the group census associated with the quote during configuration. When you select the group census group class summary records, the flow creates the corresponding quote line items for group summary and placeholder members.

1.  From the App Launcher, find and select **Product Configuration Flows**.
2.  Click **New**.
3.  Specify these details:
    1.  Enter CnfgGrpSum as the flow identifier.
    2.  Set the status to active.
4.  Save your changes.
5.  Navigate to the Related tab.
6.  In the Product Configuration Flow Assignments section, click **New**.
7.  Select [**GroupSummary** as the product classification](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_product_classification.htm&language=en_US&type=5 "Set up product classifications to group attributes and provide reusable templates. For example, you can create a GroupSummary classification to model group-level attributes like Total Members and Average Age.").
8.  Select **Dynamic Addition Flow** as the assignment type to trigger the flow automatically during configuration.
9.  Save your changes.

When you configure quotes, this flow runs automatically to pull in group summary records.

Did this article solve your issue?

Let us know so we can improve!

YesNo