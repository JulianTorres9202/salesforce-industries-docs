---
title: "Add the Claim Workflow Rules Component to the Product Details Page"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_add_wrflw_cmpont.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add the Claim Workflow Rules Component to the Product Details Page

Add the Claim Workflow Rules Component to the Product Details Page[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add the Claim Workflow Rules Component to the Product Details Page

Use Lightning App Builder to add the Claim Workflow Lightning web component to the root product details page.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From the App Launcher, find and select **Product Catalog Management**.
2.  Select a root claims product.
3.  On the root claims product details page, from Setup, select **Edit Page**.
4.  Add a new custom tab and give your tab a unique, descriptive label. For example, Claim Workflow Rules.
5.  In Lightning App Builder, drag the Underwriting Rules component to the new tab in the page layout.
6.  To choose how you want to activate the page, click **Activation**.
7.  Select the APP, RECORD TYPE, AND PROFILE tab to assign the page to a combination of Lightning apps, record types, and profiles.
8.  To show the Claim Workflow Rules component only for root products, set the record type scope to **Product** when adding assignments.
9.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo