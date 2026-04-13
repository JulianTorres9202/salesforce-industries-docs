---
title: "Set Up Underwriting Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_underwriting_rules.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up Underwriting Rules

Set Up Underwriting Rules

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Set Up Underwriting Rules

Before creating underwriting rules, set up stage management, configure rule library, and add the Underwriting Rules component to the Product details page.

[](https://help.salesforce.com/s?language=en_US)

## Set Up Stage Management

Define how quotes progress through different stages in your business process. Create a stage definition for the Quote object and configure stage transitions for each stage.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To configure Stage Management: | Stage Management Design User |
| To enable stage management for users: | Stage Management User |

[](https://help.salesforce.com/s?language=en_US)Note Before setting up Stage Management, create at least one record type for the Quote object. If you create stage definitions without record types and add record types later, the stage transitions and any rules based on those transitions become invalid.

1.  Enable the Stage Management setting.[](https://help.salesforce.com/s?language=en_US)
    1.  From Setup, in the Quick Find box, find and select **Stage Management**.
    2.  Turn on **Stage Management**.
2.  Create a stage definition.[](https://help.salesforce.com/s?language=en_US)
    1.  From the Stage Management page, click **New**.
    2.  Enter a name for the stage definition.
    3.  In the Reference Object, select **Quote**.
    4.  In the Reference Object Field, select **Status**.
    5.  If needed, select a record type for the Quote object.
    6.  Save the stage definition.
3.  Configure stage transitions to define stage movement for the Quote object. For example, define the stage transition to move the quote from the Submitted stage to the Approved stage and from the Submitted stage to the Rejected stage.[](https://help.salesforce.com/s?language=en_US)
    1.  Click the name of the stage definition to open the definition in the Stage Management console.
    2.  In the Stage Management console, to add a stage transition for the source stage, click **Add Stage Transition**.
    3.  In Transition To, select the target stage.
    4.  Click **Add**.
        
        Add stage transitions for all stages to create a stage transition plan for your business process.
        
4.  Activate the stage definition.

[](https://help.salesforce.com/s?language=en_US)

## Configure Rule Library

Rule creation requires a rule library. This library stores and runs the rules in the engine.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

1.  From the App Launcher, find and select **Rule Libraries**.
2.  Click **New**.
3.  Enter a name and API name for the rule library.
4.  Select the usage type as **Underwriting**.
5.  Enter the context definition name. This is the developer name of the context definition that is extended from InsuranceContext, for example, InsuranceContext.
6.  Save the changes.

[](https://help.salesforce.com/s?language=en_US)

## Add the Underwriting Rules Component to the Product Details Page

Use Lightning App Builder to add the Underwriting Rules Lightning web component to the root product details page.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To add the Underwriting Rules component | Digital Insurance Product Administration |

1.  From the App Launcher, find and select **Product Catalog Management**.
2.  Select a root product.
3.  On the root product details page, from Setup, select **Edit Page**.
4.  Add a new custom tab and give your tab a unique, descriptive label. For example, Underwriting Rules.
5.  In Lightning App Builder, drag the Underwriting Rules component to the new tab in the page layout.
6.  To choose how you want to activate the page, click **Activation**.
7.  Select the APP, RECORD TYPE, AND PROFILE tab to assign the page to a combination of Lightning apps, record types, and profiles.
8.  To show the Underwriting Rules component only for root products, set the record type scope to **Product** when adding assignments.
9.  Save your changes.

[](https://help.salesforce.com/s?language=en_US)

## Create Rule Evaluation Actions

Define actions for rule evaluation outcomes by using auto launched flows to automate tasks like sending emails when a rule evaluates to true or false.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with Digital Insurance Platform</td></tr></tbody></table>

Create actions for scenarios when a rule evaluates to true and when it evaluates to false. Underwriting rules support only auto launched flows for rule evaluation actions. For example, you can configure an auto launched flow with the Send Email core action to send a success email when the rule evaluates to true and a failure email when it evaluates to false.

In this example, admin sets up a flow to trigger a success email when the rule evaluates to true

1.  From Setup, in the Quick Find box, search for and select **Flows**.
2.  Click **New Flow** and select **Start from Scratch**.
3.  Click **Next**.
4.  Select **Auto Launched Flow (No Trigger)** and click **Create**.
5.  In Flow Builder, add a new **Send Email** action element.
6.  Provide the label and API name for your flow and specify email content and recipients.
7.  Save your changes.
8.  Activate the flow.

#### See Also

-   [Send Email Flow Core Action](https://help.salesforce.com/s/articleView?id=platform.flow_ref_elements_actions_sendemail.htm&language=en_US&type=5)
-   [Options for Sending Emails from Flows](https://help.salesforce.com/s/articleView?id=platform.flow_build_actions_email.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo