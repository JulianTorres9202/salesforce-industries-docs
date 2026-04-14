---
title: "Calculate and View Expected Revenue"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_rate_plan_expected_revenue.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Calculate and View Expected Revenue

Calculate and View Expected Revenue[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Calculate and View Expected Revenue

You can calculate and view expected revenue at rate plan, policy, and coverage levels.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use rate plan: | Insurance Policy Management User |

For information on how the expected revenue is calculated, see [Expected Revenue](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/connect_resources_expected_revenue.htm).

For the expected revenue that’s calculated for the rate plan to roll up to policy, the Premium Frequency on the Insurance Policy record page must be selected with an appropriate value before creating a rate plan associated rate plan commission.

1.  From an Insurance Rate Plan record, on the Insurance Rate Plan Commission related list, click **Assign New Commission**.
2.  Select a commission type and then click **Next**.
    
    Based on the commission type you select, the corresponding fields appear.
    
    | commission Type | fields |
    | --- | --- |
    | Flat Premium Percentage | Premium Percent |
    | Flat Fee Percent | Fee Percent |
    | Flat Fee | Fee Amount |
    | Graded Premium Percentage | Amount Start Range, Amount End Range, Premium Percent |
    | Capitated Fee | Fee Amount |
    | Graded Volume | Number Start Range, Number End Range, Fee Amount |
    
3.  Enter the required details in the corresponding fields for the commission type, and save your work.
    
    The Expected Revenue Amount field gets populated in the Details tab of the Insurance Rate Plan record. Also, the Expected Revenue Amount field gets populated in the associated Insurance Policy and Insurance Policy Coverage record.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo