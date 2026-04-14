---
title: "Configure Plans and Coverages for Census Members Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_configure_plan.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Plans and Coverages for Census Members Enrollment

Configure Plans and Coverages for Census Members Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Plans and Coverages for Census Members Enrollment

Manage plan and coverage selections for primary members and dependents.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To configure plans for bulk enrollment | Digital Insurance Group Enrollment, Digital Insurance Group Enrollment Customer Community, and Digital Insurance Group Enrollment Partner Community |
| To configure plans for individual enrollment | Digital Insurance Group Enrollment, Digital Insurance Group Enrollment Customer Community, and Digital Insurance Group Enrollment Partner Community |

This feature is available only when the Census Type is set to Enrollment.

1.  Click the action menu for the member you want to configure plans and coverages, and then select **Configure Plan**.
    
    Based on the group class of the group census member you’ve selected, the eligible product category and corresponding plans are shown based on the information in contract group plans group class.
    
2.  In the Configure Plan window, turn on the **Opt In** for the products you want to add. Then, select a plan from the dropdown for each product category.
3.  To opt out of any plan, turn off **Opt In**.
    
    If a primary member choses to opt out of a product category, the corresponding dependent members can’t opt for that product category.
    
4.  Click **Next**.
    
    You’ll see the selected products in individual tabs along with selected plans and a list of mandatory and optional coverages for each plan. For each of the coverages, the attributes and corresponding values are shown based on the configuration in the contract. You can opt in or opt out of the optional coverages using the Include Coverage toggle.
    
    If you have set the Execute Configuration Rules flag to true, then the product configuration rules are executed.
    
5.  Repeat these steps for each plan section, and then save your changes.
6.  To opt a dependent out of a plan that the primary member has opted for, click the action menu for dependent and select **Configure Plan**. Then turn off **Opt in** for the plan you want to opt out the dependent from.
    
    You can’t choose a plan that the primary member hasn’t opted for, but you can select a different set of optional coverage selections for a dependent.
    
7.  Select the coverages for the selected plans and save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo