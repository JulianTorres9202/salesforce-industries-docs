---
title: "Define Condition Logic for Claim Workflow Rule Groups"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_set_up_wrkflw_cndtn_logic.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Define Condition Logic for Claim Workflow Rule Groups

Define Condition Logic for Claim Workflow Rule Groups[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Define Condition Logic for Claim Workflow Rule Groups

Specify which claim workflow rules must evaluate to true for a claim to transition to the target stage by defining condition logic.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

Configure logical expressions in the Condition Logic field by using sequence numbers and operators. You can use sequence numbers to determine which rules to execute, and logical operators (AND, OR) to define how the conditions are evaluated. For example, in the expression (1 AND 2) OR 3, the quote transitions to the next stage if both rule 1 and rule 2 evaluate to true, or if rule 3 evaluates to true. The quote transitions to the next stage only if the condition logic is satisfied.

[](https://help.salesforce.com/s?language=en_US)Note Make sure that active claim workflow rules in a rule group have a condition logic expression. A blank expression causes a runtime error during rule evaluation.

1.  On the root product details page, click the **Claim Workflow Rules** tab. Depending on your organization’s configuration, this tab may have a different label.
2.  Expand the rule group that you want to configure.
3.  In Condition Logic, add a logic expression by using the logical operators (AND, OR), and sequence numbers of the rules in the group.

Did this article solve your issue?

Let us know so we can improve!

YesNo