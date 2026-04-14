---
title: "Configure Manageable Actions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_configure_manageable_actions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Manageable Actions

Configure Manageable Actions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Manageable Actions

Configure the actions that an adjuster can take based on the payment status of a claim coverage payment detail record. For example, enable the Edit, Pay, Delete, and Pay Ex Gratia actions when the payment status is Draft. Some statuses have preconfigured default actions. For example, the Paid status has a default Cancel Payment action.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From Setup, in the Quick Find box, enter Insurance Claim Services, and then select **Configure Picklist Mapping**.
2.  For the static value Draft, click , and then select **Manage Actions**.
3.  Select and move the Edit (Standard), Delete (Standard), Pay (Standard), and Pay Ex Gratia (Standard) actions from the Available list to the Selected list.
4.  Save your changes.
5.  Similarly map required actions for the other status values.

Did this article solve your issue?

Let us know so we can improve!

YesNo