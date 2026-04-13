---
title: "Manage Contribution Plans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_contribution_plan_manage.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Manage Contribution Plans

Manage Contribution Plans

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Manage Contribution Plans

Create an insurance contribution plan on the policy record and edit contribution plan line items as needed.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use contribution plan: | Insurance Policy Management User |

[](https://help.salesforce.com/s?language=en_US)

## Create Contribution Plan and Line Items

Create an insurance contribution plan for an insurance policy to determine the amount the employer charges the employee for the insurance coverage.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use contribution plan: | Insurance Policy Management User |

1.  From an Insurance policy record page, on the Insurance Contribution Plans related list, click **New**.
2.  Enter the required details.
    
    | Field Name | Description |
    | --- | --- |
    | Name | The name of the plan. |
    | Isnurance Policy | The insurance policy that the specific contribution plan applies to. |
    | Insurance Policy Coverage | The insurance policy coverage that the specific contribution plan applies to. |
    | Non Contributory | Indicates whether the employee contributes to the plan. |
    | Pre Tax | Indicates whether the contribution is pre tax. |
    | Contribution Frequency | Specifies the contribution frequency. |
    | Additional Information | Additional information about the contribution plan. |
    | Group Class | The group class of employees that's associated with the contribution plan. Only the group classes that are [mapped to the Insurance Benefits Eligibility definitions](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_benefit_eligibility_group_class_define.htm&language=en_US&type=5 "To provide more granular benefit options to your users when they use group classes, map the Insurance Benefits Eligibility definitions on an Insurance Policy or Insurance Policy Coverage record to the relevant group classes.") on an Insurance Policy are available to be associated with the contribution plan. |
    | Tier Structure | Specifies the employee tier that's associated with a specific contribution plan. |
    
    For the Group Class field, only the group classes that are [mapped](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_benefit_eligibility_group_class_define.htm&language=en_US&type=5 "To provide more granular benefit options to your users when they use group classes, map the Insurance Benefits Eligibility definitions on an Insurance Policy or Insurance Policy Coverage record to the relevant group classes.") to the Insurance Benefits Eligibility definitions on an Insurance Policy are available to be associated with the contribution plan.
    
3.  Click **Save & Add Line Items**.
    
    The contribution plan and its line items are created and an Edit Contribution Plan Line Items window opens.
    
4.  Enter the contribution amount and premium percent for each line item.
5.  Save your changes.

[](https://help.salesforce.com/s?language=en_US)

## Edit Contribution Plan Line Items

To update an existing contribution plan, edit the associated line items.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use contribution plan: | Insurance Policy Management User |

1.  From an Insurance Policy or Insurance Policy Coverage record, on the Insurance Contribution Plans related list, from the dropdown menu for the contribution plan, click **Edit Line Items**.
2.  Update the Amount and Premium Percent fields for individual line items.
3.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo