---
title: "Example: Create a Custom Flow for Underwriting Rule Evaluation"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_execute_underwriting_rule.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Example: Create a Custom Flow for Underwriting Rule Evaluation

Example: Create a Custom Flow for Underwriting Rule Evaluation[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Example: Create a Custom Flow for Underwriting Rule Evaluation

Set up a flow to trigger underwriting rule evaluation. This flow uses an Apex class to call the Underwriting Rules Invoke API directly from the Quote record.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

This example shows the basic approach to executing underwriting rules. You can customize the flow and API behavior based on your business requirements.

1.  Create an Apex class to send the Quote ID and To Stage values from a flow to the Insurance Underwriting Rules Invoke API. This class sends a POST request to the Underwriting Rules Invoke API, and then returns the underwriting rule API names and their execution status.
2.  Create a custom screen flow to take user inputs and evaluate underwriting rules.
    
    | Element Type | element name | components | Description |
    | --- | --- | --- | --- |
    | Screen | Enter Inputs | 
    Text Input: Quote ID
    
    Text Input: To Stage
    
     | Collects user inputs for the flow. |
    | Action | Send POST Request | \- | Calls the Apex class to send a POST request to the Insurance Underwriting Rules Invoke API. |
    | Screen | Display Results | Display Text: Underwriting Rule Details | Displays the API response from the Action element, which includes underwriting rule API names and their execution status. |
    
3.  Create a custom button for the Quote object.
4.  From the Object Manager, link the custom button to the flow.

After the product admins create a custom button and configure the custom flow, insurance reps can click the custom button and provide required input to launch the flow.

Did this article solve your issue?

Let us know so we can improve!

YesNo