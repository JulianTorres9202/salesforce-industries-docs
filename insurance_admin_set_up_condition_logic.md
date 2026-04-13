---
title: "Define Condition Logic for Underwriting Rule Groups"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_condition_logic.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Define Condition Logic for Underwriting Rule Groups

Define Condition Logic for Underwriting Rule Groups[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Define Condition Logic for Underwriting Rule Groups

Specify which underwriting rules must evaluate to true for a quote to transition to the target stage by defining condition logic.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

Configure logical expressions in the Condition Logic field by using sequence numbers and operators. You can use sequence numbers to determine which rules to execute, and logical operators (AND, OR) to define how the conditions are evaluated. For example, in the expression (1 AND 2) OR 3, the quote transitions to the next stage if both rule 1 and rule 2 evaluate to true, or if rule 3 evaluates to true. The quote transitions to the next stage only if the condition logic is satisfied.

[](https://help.salesforce.com/s?language=en_US)Note Make sure that active underwriting rules in a rule group have a condition logic expression. A blank expression causes a runtime error during rule evaluation.

1.  On the root product details page, click the **Underwriting Rules** tab. Depending on your organization’s configuration, this tab may have a different label.
2.  Expand the rule group that you want to configure.
3.  In Condition Logic, add a logic expression by using the logical operators and sequence numbers of the rules in the group.

Did this article solve your issue?

Let us know so we can improve!

YesNo