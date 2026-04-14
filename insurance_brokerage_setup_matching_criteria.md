---
title: "Configure Matching Criteria for an Insurance Policy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_setup_matching_criteria.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Matching Criteria for an Insurance Policy

Configure Matching Criteria for an Insurance Policy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Matching Criteria for an Insurance Policy

Identify the policy IDs for commission processing by mapping the insurance policy fields with the commission statement line item fields.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To set up brokerage: | Insurance Brokerage User |

1.  In Setup, find and select **Brokerage**. Then, select **Commissions Management.**
2.  In the Matching Criteria field, specify the criteria to be used to identify the policy ID.
3.  [](https://help.salesforce.com/s?language=en_US)Note Specify the criteria in <Commission Statement line Item field>:<Insurance Policy field> format. For example, to search the InsPolField1, InsPolField2, and InsPolField3 fields of the insurance policy, specify the criteria as CSLIField1:InsPolField1, CSLIField2:InsPolField2 AND CSLIField3:InsPolField3.
    
    Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo