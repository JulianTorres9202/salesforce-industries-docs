---
title: "Set Up Your Org to Support Rate Plans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_rate_plan_org.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Your Org to Support Rate Plans

Set Up Your Org to Support Rate Plans

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Set Up Your Org to Support Rate Plans

Configure your Salesforce org to make Rate Plans available to your users.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use rate plan: | Insurance Policy Management User |

[](https://help.salesforce.com/s?language=en_US)

## Add the Rate Plan Related List to the Record Pages

To make the Rate Plan related list available to your users, add it to the page layout.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use rate plan: | Insurance Policy Management User |

1.  From the object management settings for the Insurance Policy object, go to **Page Layouts**.
2.  On the layout assigned to your users, click **Edit**.
3.  Click **Related Lists**.
4.  Drag Insurance Rate Plans from the available options and drop it onto the layout.
5.  Save your changes.
6.  Similarly, update the **Insurance Policy Coverage** object.

[](https://help.salesforce.com/s?language=en_US)

## Add the Expected Revenue Amount Field

To view the expected revenue on Insurance Policy and Insurance Policy Coverage record pages, add the Expected Revenue Amount field on the respective record pages.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use rate plan: | Insurance Policy Management User |

1.  From the Object Manager, open the **Insurance Policy** object.
2.  Click **Page Layouts** and select **Insurance Policy Layout**.
3.  From the Fields section, drag **Expected Revenue Amount** field and drop it at the desired location on the page layout.
4.  Save your changes.
5.  Similarly, update the **Insurance Policy Coverage** object.

Did this article solve your issue?

Let us know so we can improve!

YesNo