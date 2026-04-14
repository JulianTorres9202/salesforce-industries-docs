---
title: "Configure the Batch Job to Create Portal Users"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_portal_users_batch_job.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Batch Job to Create Portal Users

Configure the Batch Job to Create Portal Users[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Batch Job to Create Portal Users

The out-of-the-box Group Enrollment batch job references the Group Enrollment flow that’s shipped out of the box and can’t be modified. Perform this task to ensure the batch job uses the flow that’s customized to create portal users.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To configure batch job for bulk enrollment | Digital Insurance Group Enrollment, Digital Insurance Group Enrollment Customer Community, and Digital Insurance Group Enrollment Partner Community |
| To configure batch job for individual enrollment | Digital Insurance Group Enrollment, Digital Insurance Group Enrollment Customer Community, and Digital Insurance Group Enrollment Partner Community |

1.  From Setup, in the Quick Find box, enter Batch Management, then select **Batch Management**.
2.  Click **New**.
3.  In the New batch job window, enter these details:
    
    -   Name: Enter a name for the batch job
    -   API Name: Enter and API name for the batch job
    -   Process Type: Flow
    -   Execution Process: Select the flow that’s configured to create portal users
    -   Group: InsuranceGroupBenefits
    -   Batch Size: 4
    -   Retry Count: 1
    -   Retry Interval: 1000
    
4.  Click **Next** and then provide these values:
    
    -   Flow Input Variable: groupCensusMemberId
    -   Object: Group Census Member
    -   Conditions:
        -   Select Records When: All Conditions Are Met (AND)
        -   Condition 1: Group Census ID Equals Input Variable groupCensusId
        -   Condition 2: Association with Primary Member Equals Value Self
    
5.  Save and then activate the batch job.

Did this article solve your issue?

Let us know so we can improve!

YesNo