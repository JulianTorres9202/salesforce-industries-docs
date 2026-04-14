---
title: "Configure Payment Detail for Claims Financials"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_configure_payment_detail.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Payment Detail for Claims Financials

Configure Payment Detail for Claims Financials[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Payment Detail for Claims Financials

Customize the Claim Coverage Payment Detail (CCDP) intake form and override default calculations.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From Setup, in the Quick Find box, enter Insurance Claim Services, and then select **Configure Payment Processing**.
2.  Click **New Loss Item Mapping** or **New Expense Item Mapping.**
3.  Select the coverage for which you want to create a custom layout. For example, Vandalism Coverage.
4.  Select a field set. To create a field set , see [Create Field Sets](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_fld_set.htm&language=en_US&type=5 "Salesforce has a drag-and-drop WYSIWYG tool for creating field sets.").
5.  (For Loss Items only) Optionally, override the default calculation logic for calculating adjustments or processing limits.
    1.  Select Expression Set or Integration Procedure.
    2.  Select the definition for the selected expression set or integration procedure.
6.  Click **Active** to activate the mapping.
7.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo