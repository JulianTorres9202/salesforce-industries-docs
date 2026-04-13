---
title: "Set Up Configuration Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_configuration_rules.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up Configuration Rules

Set Up Configuration Rules

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Set Up Configuration Rules

Define and invoke configuration rules when configuring products.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configurator is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

| Permission set |
| --- |
| To set up configuration rules: | Product Configuration Rules Designer |

Note Assign the Product Configurator permission set to allow users to execute rules from the Quotes UI at runtime.

[](https://help.salesforce.com/s?language=en_US)

## Create a Rule Library

Rule creation requires a rule library. This library stores and runs the rules in the rule engine.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configurator is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

1.  From the App Launcher, find and select **Rule Libraries**.
2.  Click **New**.
3.  Enter a name and API name for the rule library.
4.  Select **Configurator** as the usage type.
5.  Enter the context definition name. This is the developer name of the context definition that is extended from InsuranceContext. For example, InsuranceContext.
6.  Save the changes.

[](https://help.salesforce.com/s?language=en_US)

## Activate a Rule Library Version

Use the rule library version to store and run rules in the rule engine.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configurator is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

1.  From the App Launcher, find and select **Rule Libraries**.
2.  Click the rule library that contains the version you want to activate.
3.  On the Related tab, click the rule library version that you want to activate.
4.  In the global action menu, click **Activate**.

[](https://help.salesforce.com/s?language=en_US)

## Enable Configuration Rules

Grant users access to configuration rules.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where Product Configurator is enabled with the Revenue Lifecycle Management add-on</td></tr></tbody></table>

1.  In Setup, in the Quick find box, find and select **Revenue Settings**.
2.  Turn on **Set Up Configuration Rules**.

Did this article solve your issue?

Let us know so we can improve!

YesNo