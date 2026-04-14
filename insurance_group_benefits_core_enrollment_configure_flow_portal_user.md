---
title: "Configure the Salesforce Flow for Enrollment to Create Portal Users"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_enrollment_configure_flow_portal_user.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Salesforce Flow for Enrollment to Create Portal Users

Configure the Salesforce Flow for Enrollment to Create Portal Users[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Salesforce Flow for Enrollment to Create Portal Users

You can use the out-of-the-box (OOTB) Group Enrollment flow to enroll group census members and create insurance policies based on their plan and coverage selection in the group census member plan.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Expereince</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To configure flow for bulk enrollment: | Digital Insurance Group Enrollment and Digital Insurance Group Enrollment Partner Community |
| To configure flow for individual enrollment: | Digital Insurance Group Enrollment, Digital Insurance Group Enrollment Customer Community, and Digital Insurance Group Enrollment Partner Community |

The OOTB flow doesn’t create portal users. If you want to create portal users for the census members, you can customize the flow.

1.  From Setup, in the Quick Find box, enter Flows, then select **Flows**.
2.  Click the **Enroll Member** flow.
3.  Enter a name for the new flow and leave the other input parameters unchanged.
4.  In the flow canvas, select **Create Contacts And Users From Group Census Or Members invocable action**.
5.  Set Create Portal User to **True** and provide a valid Profile ID.
    
    If your org has person account enabled, perform step 5 and 6 for Create Accounts And Users From Group Census Or Members invocable action.
    
6.  Save and activate the flow.
7.  Add this flow to the Batch Management configured for enrollment.

Did this article solve your issue?

Let us know so we can improve!

YesNo