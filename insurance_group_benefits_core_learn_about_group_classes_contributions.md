---
title: "Learn About Group Classes and Group Class Contributions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_learn_about_group_classes_contributions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Learn About Group Classes and Group Class Contributions

Learn About Group Classes and Group Class Contributions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Learn About Group Classes and Group Class Contributions

Group classes are groups of members who all receive similar benefits. Examples of group classes include Executives, Managers, and Directors. Group class contributions have details about the benefits provided by the employer for a group class.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

## Group Classes

To set up up a group class, users go to a Group Class page and click **New**.Each group class must have a name and account. To configure processes that validate whether a group class is active, use the **Effective Start Date** and **Effective End Date** fields in each group class record.

Tip Edit the Group Class search layout to move the Account field below the Name field. This makes it easier to differentiate the associated group classes for an account when you add new members.

Note You can't provide a value for the **Parent Group Class** field while adding or updating a group class even though the field is available on the group class entity. This is to avoid circular relationship between group classes.

## Group Class Contributions

After adding the group class for a given account, users go to a Group Class Contribution page and click **New**..

Each group class contribution must have a **Name** and a corresponding **Group Class**. To validate whether the group class contribution is active, use the **Effective Start Date** and **Effective End Date** fields in each group class contribution record.

For **Type**, specify whether the employer contribution is a percentage of the total premium or a fixed amount no matter what the total premium is. For **Amount**, enter the corresponding percentage or amount.

Specify **Member Type** as either Subscriber or Dependent.

Each group class must be linked to at least one of these fields: **Contract Group Plan**, **Group Benefit Product Category**, or **Product**.

Did this article solve your issue?

Let us know so we can improve!

YesNo