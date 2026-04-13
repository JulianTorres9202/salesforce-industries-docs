---
title: "Manage Policy Lifecycle Processes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_policy_lifecycle_manage_processes.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Manage Policy Lifecycle Processes

Manage Policy Lifecycle Processes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Manage Policy Lifecycle Processes

Use the policy lifecycle actions to renew, endorse, repurpose, or cancel a policy with minimal data entry.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To use policy lifecycle actions: | Context Service Runtime, FSC Insurance, Insurance Brokerage Commission Management, Insurance Brokerage Policy Management, Insurance Brokerage User |

For an Insurance Policy page to show the appropriate field labels when performing policy lifecycle processes, add the fields to the Insurance Policy object.

Renew an existing insurance policy by using the Renew action.

Create a new insurance policy from an existing one by just adding the new property details using the Endorse action. A new policy with the updated details is created and the existing policy is canceled.

Create a new insurance policy that inherits structure and details from an existing policy using the Repurpose action. Cancel a policy that you no longer want to use using the Cancel action.

1.  From the App Launcher, find and select **Insurance Policies**, and then select the policy that you want to renew, endorse, repurpose, or cancel.
2.  On the Insurance Policy record page, select an appropriate action.
    -   To renew a policy with the same or different carrier, select **Renew** .
    -   To endorse a policy, select **Endorse**.
    -   To repurpose a policy, select **Repurpose**.
    -   To cancel a policy, select **Cancel**.
3.  To renew or cancel multiple insurance policies at once, from an account record page, select the insurance policies from list view and select **Renew Policies** or **Cancel Policies**.

Did this article solve your issue?

Let us know so we can improve!

YesNo