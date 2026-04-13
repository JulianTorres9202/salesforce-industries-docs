---
title: "Product Underwriting Rules for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_product_underwriting_rules.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Product Underwriting Rules for Insurance

Product Underwriting Rules for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Underwriting Rules for Insurance

Define the criteria for transitioning a quote record to the target stage. Product underwriting rules set the conditions for the root product that determine the quote's progress. After you define stage definitions and configure stage transitions, create underwriting rules to define the transition criteria for those stages.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

| Permission set license | Description |
| --- | --- |
| Digital Insurance Product Administration | Allows users to create underwriting rules. |
| Industries Stage Management Addon |

| User Permissions Needed |
| --- |
| To access objects and interfaces required to configure underwriting rules | Fulfilment Designer |

These rules apply conditions and actions at different stages of a quote record and evaluate whether the quote can move to the target stage. Depending on the evaluation outcome, the quote record either advances to the target stage or remains in its current stage.

When configuring these rules, specify actions for both true and false outcomes. For example, you can create a rule to move a quote from Submitted to Underwriter Review stage if the Risk Category for the Auto Driver product is High.

[](https://help.salesforce.com/s?language=en_US)

**Underwriting Rules Flow**

[](https://help.salesforce.com/s?language=en_US)![Underwriting Rules Flow](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-insurance-260-0-0-production-enus/e4c2671d-0822-4c56-95dd-073f2b1f9ddc/insurance/images/u-v/underwriting_intro.png)

## Considerations for Using Underwriting Rules

[](https://help.salesforce.com/s?language=en_US)

-   Use underwriting rules to define conditions for a specific root product, rather than for an entire object type such as Quote. While rules configured in Stage Management apply to transitions across all quotes, product underwriting rules apply to a single root product.
-   Keep in mind the distinction between Stage Management and underwriting rules. Use Stage Management to define stage definitions and configure stage transitions. Use underwriting rules to define criteria and actions for those stage transitions. Underwriting rules offer greater flexibility and are best suited for stage transitions at the root product level.

-   **[Set Up Underwriting Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_underwriting_rules.htm&language=en_US&type=5#insurance_admin_set_up_underwriting_rules)**  
    Before creating underwriting rules, set up stage management, configure rule library, and add the Underwriting Rules component to the Product details page.
-   **[Configure Sharing Rules for Customer Community Users](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_underwriting_sharing_settings.htm&language=en_US&type=5)**  
    Sharing rules give customer community users access to records that are relevant for using underwriting rules.
-   **[Create an Underwriting Rule](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_underwriting_rules.htm&language=en_US&type=5)**  
    Define conditions for quote transitions and configure actions for both true and false evaluations. The quote progresses to the target stage if the root product meets the specified criteria.
-   **[Underwriting Rule Groups](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_underwriting_rule_groups.htm&language=en_US&type=5)**  
    Underwriting rules are organized into groups based on object type and transition step. For example, Rule Group - Quote, Draft to Approved includes all rules that apply to the Draft to Approved stage transition for the Quote object.
-   **[Example: Quote Transition from Submitted to Approved](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_quote_transition.htm&language=en_US&type=5)**  
    This example demonstrates how a Product Admin can configure conditions to transition a quote from Submitted to either Approved or Underwriter Review.
-   **[Evaluation of Underwriting Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_underwriting_rule_evaluation.htm&language=en_US&type=5)**  
    You can evaluate the underwriting rules at runtime for a quote record by using the Insurance Invoke Underwriting Rules connect API.
-   **[Track the Results of Underwriting Rule Evaluations](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_track_underwriting_rule_results.htm&language=en_US&type=5)**  
    View the history of underwriting rule execution on the Stage Transition Underwriting Evaluations page.

Did this article solve your issue?

Let us know so we can improve!

YesNo