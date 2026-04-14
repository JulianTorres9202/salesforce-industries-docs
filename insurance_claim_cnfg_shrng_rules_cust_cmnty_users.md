---
title: "Configure Sharing Rules for Customer Community Users"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_cnfg_shrng_rules_cust_cmnty_users.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Sharing Rules for Customer Community Users

Configure Sharing Rules for Customer Community Users[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Sharing Rules for Customer Community Users

Sharing rules give customer community users access to records that are relevant for using claim workflow rules.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From Setup, in the Quick Find box, find and select **Sharing Settings**.
2.  Click **Edit**.
3.  Now set these object values for the default internal access and default external access:
    
    | object | default internal access | default external access |
    | --- | --- | --- |
    | Stage Transition Underwriting Evaluation | Public Read & Write | Public Read & Write |
    | Underwriting Rule Group | Public Read Only | Public Read Only |
    
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo