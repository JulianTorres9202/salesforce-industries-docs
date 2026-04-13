---
title: "Policy Lifecycle Processes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_policy_lifecycle_processes.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Policy Lifecycle Processes

Policy Lifecycle Processes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Policy Lifecycle Processes

Insurance Brokers manually maintain their own data to mirror what's in the carrier system due to lack of integration between the carrier and the broker systems. This manual process can be cumbersome, especially when there's very little difference between an existing Insurance Policy in their system and the new one they are trying to create. The policy lifecycle processes help representatives manage policies efficiently with minimal data entry by providing actions to renew, endorse, repurpose, and cancel policy.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

The InsBrokeragePolicyContext context definition is a standard context definition used to retrieve and manage policy data for Insurance Brokerage policy operations and services. This context definition is shipped out of the box and includes default fields for each action. You can update these fields to display or extend this definition according to your business requirements.

| Action | Fields |
| --- | --- |
| 
Renew

 | 

Name, Name Insured, Writing Carrier Account, Status, Effective From Date, Billing Carrier Account, Effective To Date, Actual Renewal Date, Line Of Business, Line Of Coverage, Premium Frequency, Renewed Policy, Underwriting Entity

 |
| 

Endorse

 | 

Name, NameInsured, Writing Carrier Account, Status, Effective From Date, Billing Carrier Account, Effective To Date, Actual Renewal Date, Line Of Business, Line Of Coverage, Premium Frequency, Underwriting Entity

 |
| 

Repurpose

 | 

Name, NameInsured, Writing Carrier Account, Status, Effective From Date, Billing Carrier Account, Effective To Date, Actual Renewal Date, Line Of Business, Line Of Coverage, Premium Frequency, Underwriting Entity

 |

-   **[Create Custom Context Definition and Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_create_custom_defintion_mapping.htm&language=en_US&type=5)**  
    Customise the InsBrokeragePolicyContext context definition to meet your business requirements.
-   **[Manage Policy Lifecycle Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_policy_lifecycle_manage_processes.htm&language=en_US&type=5)**  
    Use the policy lifecycle actions to renew, endorse, repurpose, or cancel a policy with minimal data entry.

Did this article solve your issue?

Let us know so we can improve!

YesNo