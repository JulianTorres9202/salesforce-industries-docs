---
title: "Assign a Permission Set to Portal Users"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_assign_a_permission_set_to_portal_users.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Assign a Permission Set to Portal Users

Assign a Permission Set to Portal Users[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Assign a Permission Set to Portal Users

Create and assign a permission set for portal users to grant the license and permissions they need to access the Insurance Policyholder Portal.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To create permission sets:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Manage Profiles and Permission Sets</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To assign permission sets:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Assign Permission Sets</td></tr></tbody></table>

1.  From Setup, in the Quick Find box, enter Permission Sets, and then select **Permission Sets**.
2.  Click **New**.
3.  Provide a name for the permission set, for example, FSC Insurance.
4.  For License, select **FSC Insurance**, and then save your changes.
5.  From Setup, in the Quick Find box, enter Users, and then select **Users**.
6.  Click a user who’s assigned one of the customer community profiles.
7.  In Permission Set Assignments, click **Edit Assignments**.
8.  From Available Permission Sets, select the permission set that you created and an appropriate user profile permission set. For example, if the customer user profile is Customer Community Plus Login User, select FSC Insurance as the user profile permission set.
9.  Click **Add**.
10.  Save your changes.
11.  Create an OmniStudio permission set for your portal users. See [Create an OmniStudio Permission Set for Standard Experience Users](https://help.salesforce.com/s/articleView?id=xcloud.os_create_an_omnistudio_permission_set_for_standard_experience_users_7203.htm&language=en_US&type=5).
12.  Assign the OmniStudio permissions set to your portal users. See [Assign the OmniStudio Permission Set or Group to Standard Experience Site Users](https://help.salesforce.com/s/articleView?id=xcloud.os_assign_the_omnistudio_permission_set_or_group_to_standardexperience_users_7452.htm&language=en_US&type=5).

Did this article solve your issue?

Let us know so we can improve!

YesNo