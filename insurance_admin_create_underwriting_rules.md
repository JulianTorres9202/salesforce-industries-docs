---
title: "Create an Underwriting Rule"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_underwriting_rules.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create an Underwriting Rule

Create an Underwriting Rule[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create an Underwriting Rule

Define conditions for quote transitions and configure actions for both true and false evaluations. The quote progresses to the target stage if the root product meets the specified criteria.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

| Permission set license | Description |
| --- | --- |
| Digital Insurance Product Administration | Allows users to create underwriting rules. |
| Industries Stage Management Addon |

| User Permissions Needed |
| --- |
| To access objects and interfaces required to configure underwriting rules | Fulfilment Designer |

Make sure the flows for True and False evaluation actions are configured.

1.  From the App Launcher, find and select **Product Catalog Management**.
2.  Select a root product.
3.  From the root product details page, click the **Underwriting Rules** tab.
    
    Depending on your organization’s customization, this tab may have a different label.
    
4.  Click **New Rule**.
5.  Select the object type as **Quote**.
6.  If needed, select a record type.
7.  Select a transition step that specifies the object’s transition from one state to another if the rule evaluates to true.
    
    For example, a quote can move from the Approved stage to the Issued stage. These transitions are predefined in Stage Management for the selected combination of object type and record type.
    
8.  Enter a name and description for the underwriting rule.
9.  Select the rule status. The rule must be active for the rule to take effect.
10.  Select a start and end date.
11.  Click **Next**.
12.  In Root Product, make sure that the root product you launched the rules from is selected by default.
13.  In Scope, click **Search Products** and select a product in the root product hierarchy. For example, if the hierarchy includes Auto and Driver, you can set the scope to either Auto or Driver. If the scope is Driver, you can define rule conditions for Driver and its direct ancestors in the product hierarchy.
14.  Specify the rule conditions.[](https://help.salesforce.com/s?language=en_US)
     1.  From Value, select a product. This field includes the product selected in Scope and its direct ancestors in the root product hierarchy.
     2.  To define criteria against the attributes of the product selected in Value, click **Add Attribute**. Each rule supports up to 5 conditions and 5 sub-conditions. Only the AND operator is supported between conditions. The rule executes only when all the conditions are met.
     3.  Click **Add Field** to define criteria against the context fields. The context fields are retrieved from the context definition linked to the rule library.
15.  Click **Next**.
16.  Click **Add Action** to define actions performed when the rule evaluates to true and when it evaluates to false.[](https://help.salesforce.com/s?language=en_US)
     1.  Select the rule evaluation type: True or False.
     2.  Enter an action name.
     3.  In Action Type, select **Automated Flow**.
     4.  Enter the Flow Definition API name to trigger the predefined flow.
17.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo