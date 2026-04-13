---
title: "Create a Configuration Rule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_configuration_rule.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create a Configuration Rule

Create a Configuration Rule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Configuration Rule

Reduce configuration errors and easily manage product validation and compatibility by applying configuration rules.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configurator is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create a configuration rule: | Product Configuration Rules User |

Configuration rules define product behavior through scope, conditions, and actions. Each rule supports up to 3 conditions, 8 subconditions, and 3 actions.

[](https://help.salesforce.com/s?language=en_US)

-   Rule Scope: When the rule scope is Bundle, the configuration rule executes within the boundaries of the root product of the bundle. When the Rule Scope is Product, the configuration rule executes for the product irrespective of where the product is in the root product hierarchy. When the rule scope is Transaction, the configuration rule executes at the transaction level (quote) beyond the existing bundle or product.
-   Conditions: Only the AND logical operator is supported between conditions. The rule executes only when all the conditions are met.
-   Actions: The Lock option restricts changes to the attribute or field at runtime. You can add a message for each action. The type of message depends on the type of action.

1.  From App Launcher, find and select **Product Catalog Management**.
2.  From the Product Catalog Management app’s home page, click **Product Configuration Rules**.
3.  Click **New**.
4.  In the Rules Details page, specify these details:[](https://help.salesforce.com/s?language=en_US)
    1.  Enter a name and description for the configuration rule.
    2.  Enter the rule duration.
    3.  Select the rule status. Set the status to Active for the rule to take effect.
    4.  To determine when this rule runs, enter the rule sequence.
        
        Rules with lower numbers run first when multiple rules are triggered at once.
        
5.  Click **Next**.
6.  In the Rules Criteria page, specify rule scope, conditions, and actions.[](https://help.salesforce.com/s?language=en_US)
    1.  Select the Rule Scope.
    2.  Specify the condition to execute the rule.
        
        When configuring rule conditions in Insurance, the resource type for each condition must be set to Product. Product Classification isn't supported.
        
    3.  Specify the action to be taken when the conditions are met.
7.  Save your changes.

-   **[Example: Automatically add a Required Product](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_add_required_product.htm&language=en_US&type=5)**  
    The admin wants to automatically add comprehensive coverage to the quote if the driver belongs to the state of Texas and prevent users from removing it.
-   **[Example: Set an Attribute Value](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_set_attribute_value.htm&language=en_US&type=5)**  
    The admin creates a SetAttribute rule to set the Collision Coverage Deductible to $500 when the Collision Coverage BI Person Limit exceeds $10,000.
-   **[Example: Create a User Profile-Based Rule](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_create_user_profile_rule.htm&language=en_US&type=5)**  
    The admin creates a UserProfileRule to automatically set the Comprehensive Coverage Deductible to $250 when a user with the Broker profile selects Comprehensive Coverage.

Did this article solve your issue?

Let us know so we can improve!

YesNo