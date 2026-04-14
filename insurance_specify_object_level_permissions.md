---
title: "Specify Object-Level Permissions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_specify_object_level_permissions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Specify Object-Level Permissions

Specify Object-Level Permissions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Specify Object-Level Permissions

Grant your portal users the object permissions required to create service requests for insurance service processes in the Insurance Client Portal.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To edit object permissions:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Manage Profiles and Permission Sets</p><p lwc-3eigj2skqo3="">AND</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Customize Application</p></td></tr></tbody></table>

1.  From Setup, in the Quick Find box, enter Profiles, and then select **Profiles**.
2.  Edit the cloned community user profile.
3.  Configure these object permissions.
    
    | Object | Access Level |
    | --- | --- |
    | Accounts | Read |
    | Cases | Read, Edit, and Create |
    | Service Catalog Requests | Read, Edit, and Create |
    | Insurance Policies | Read |
    | Omni Data Transformations | Read |
    | Omni UI Cards | Read |
    | Producers | Read |
    | Insurance Policy Assets | Read |
    | Insurance Policy | Read |
    | Insurance Policy Participants | Read |
    

Did this article solve your issue?

Let us know so we can improve!

YesNo