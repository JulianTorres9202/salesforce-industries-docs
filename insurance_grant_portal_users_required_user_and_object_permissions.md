---
title: "Grant Portal Users Required User and Object Permissions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_grant_portal_users_required_user_and_object_permissions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Grant Portal Users Required User and Object Permissions

Grant Portal Users Required User and Object Permissions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Grant Portal Users Required User and Object Permissions

Grant your portal users the needed user and object permissions to create service requests, schedule appointments, and browse knowledge articles in the Insurance Policyholder Portal.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To edit object permissions and to set field-level security:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Manage Profiles and Permission Sets AND Customize Application</td></tr></tbody></table>

1.  From Setup, in the Quick Find box, enter Profiles, and then select **Profiles**.
2.  Edit the cloned community user profile.
3.  Configure these object permissions.
    
    | OBJECT LEVEL | ACCESS LEVEL |
    | --- | --- |
    | Accounts | Read |
    | Cases | Read, Edit, and Create |
    | Claim | Read |
    | Claim Participant | Read |
    | Claim Item | Read |
    | Claim Coverage | Read |
    | Claim Coverage Payment Details | Read |
    | Claim Coverage Reserve Adjustments | Read |
    | Claim Coverage Reserve Adjustment Layout | Read |
    | Claim Coverage Reserve Details | Read |
    | Claim Payment Summaries | Read |
    | Contacts | Read |
    | Document Checklist Items | Read, Edit, and Create |
    | Engagement Channel Type | Read |
    | Insurance Policy | Read, Create |
    | Insurance Policy Coverages | Read, Create |
    | Insurance Policy Participant | Read, Create |
    | Insurance Policy Asset | Read, Create |
    | Insurance Policy Member Asset | Read, Create |
    | Omni Data Transformations | Read |
    | Omni Data Transformations Items | Read |
    | Omni Processes | Read |
    | Omni Process Compilations | Read |
    | Omni Process Elements | Read |
    | Omni UI Cards | Read |
    | Operating Hours | Read |
    | Service Catalog Requests | Read, Edit, and Create |
    | Service Resources | Read |
    | Service Territories | Read |
    | Shifts | Read |
    | Survey Invitations | Read |
    | Survey Responses | Read, Edit, and Create |
    | Surveys | Read |
    
4.  Save your changes.
5.  Update field-level security for the Case Source field on the Case object.
    1.  In Setup, go to **Object Manager**.
    2.  In the Quick Find box, enter Case, and select **Case**.
    3.  Select **Fields & Relationships**.
    4.  Select **Case Source**.
    5.  Click **Set Field-Level Security**.
    6.  For the cloned community user profile, select **Visible** and deselect **Read-Only**.
    7.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo