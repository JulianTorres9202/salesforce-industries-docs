---
title: "Create Rule Evaluation Actions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_crt_rule_evltn_actions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Rule Evaluation Actions

Create Rule Evaluation Actions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Rule Evaluation Actions

Define actions for rule evaluation outcomes by using auto-launched flows to automate tasks such as sending emails when a rule evaluates to true or false.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

Create actions for scenarios when a rule evaluates to true and when it evaluates to false. Claim workflow rules support only auto-launched flows for rule evaluation actions. For example, you can configure an auto-launched flow with the Send Email core action to send a success email when the rule evaluates to true and a failure email when it evaluates to false.

In this example, the admin sets up a flow to trigger a success email when the rule evaluates to true.

1.  From Setup, in the Quick Find box, search for and select **Flows**.
2.  Click **New Flow** and select **Start from Scratch**.
3.  Click **Next**.
4.  Select **Auto Launched Flow (No Trigger)** and click **Create**.
5.  In Flow Builder, add a new **Send Email** action element.
6.  Provide the label and API name for your flow and specify email content and recipients.
7.  Save your changes.
8.  Activate the flow.

Did this article solve your issue?

Let us know so we can improve!

YesNo