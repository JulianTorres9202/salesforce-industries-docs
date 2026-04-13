---
title: "Assign Producer Split Arrangement to Policy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_producer_split_assign_policy.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Assign Producer Split Arrangement to Policy

Assign Producer Split Arrangement to Policy

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Assign Producer Split Arrangement to Policy

Assign a producer split to an insurance policy either from an account or from outside of an account.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To assign producer split arrangement to policy: | Insurance Commissions Management and Insurance Brokerage User |

[](https://help.salesforce.com/s?language=en_US)

## Assign Producer Split Arrangement from Account

Assign producer split to an insurance policy from an account.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To assign producer split arrangement from account: | Insurance Commissions Management and Insurance Brokerage User |

1.  From the policy record page, on the Producer Split Assignment related list, click **Assign New Arrangement**.
2.  Click **Assign Producer Split Arrangement from Account**, and click **Next**.
3.  In the Assign Producer Split Arrangement from Account window, specify these values.
    
    | Field | description |
    | --- | --- |
    | Type | The type of split arrangement. The field is auto-populated if the split arrangement type is defined for the insurance policy. |
    | Line of Business | The type of split arrangement. The field is auto-populated if the split arrangement type is defined for the insurance policy. |
    | Line of Coverage | The line of coverage associated with the producer split arrangement. If the line of business is defined at the policy level, then this field is autopopulated. |
    | Split Arrangement | The split arrangement associated with the policy. |
    | Offset Duration (In Months) | The duration after which the next split arrangement becomes effective or the current split arrangement ends. For example, if the effective date for the first split arrangement is 11/26/2024 and you specify an offset duration of 3 months in the second split arrangement, the end date for the first split arrangement becomes 2/26/2025 and the effective date for the second split arrangement becomes to 2/27/2025. |
    | Effective Date | The date that the producer split arrangement is effective from. |
    | End Date | The end date of the producer split arrangement. |
    
4.  Save your work.
    
    A message confirms that the producer split arrangement is assigned.
    

[](https://help.salesforce.com/s?language=en_US)

## Assign Producer Split Arrangement from Outside of Account

Assign a new producer split to an insurance policy that’s not part of an account.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Professional</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To assign producer split arrangement from outside of account: | Insurance Commissions Management and Insurance Brokerage User |

1.  From the policy record page, on the Producer Split Assignment related list, click **Assign New Arrangement**.
2.  Select **Assign Producer Split Arrangement from Outside of Account**, and click **Next**. Select the required fields.
3.  Select the required fields.
    
    Line of Business and Line of Coverage are populated if they’re available for the selected policy.
    
4.  Save your work.
    
    A message confirms that the producer split arrangement has been assigned.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo