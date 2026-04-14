---
title: "Configure Field-Level Security"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_field_level_security.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Field-Level Security

Configure Field-Level Security[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Field-Level Security

Give your portal users access to the fields that they need for using the prebuilt insurance service processes on the Insurance Client Portal.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To set field-level security:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Manage Profiles and Permission Sets</p><p lwc-3eigj2skqo3="">AND</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Customize Application</p></td></tr></tbody></table>

1.  In Setup, go to Object Manager.
2.  Locate each object listed in this task, and click **Fields & Relationships**.
3.  For each object and field, update the field-level security as shown in this table for the profiles that use the insurance service processes.
    
    <table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:33.33333333333333%" lwc-3eigj2skqo3=""><col style="width:33.33333333333333%" lwc-3eigj2skqo3=""><col style="width:33.33333333333333%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">OBJECT</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">FIELD</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">FIELD-LEVEL SECURITY</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" rowspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3="">Case</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Account Name</td><td style="vertical-align:top;" rowspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3="">For the profiles using the insurance service processes, select Visible and deselect Read Only.</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Case Source</td></tr></tbody></table>
    

Did this article solve your issue?

Let us know so we can improve!

YesNo