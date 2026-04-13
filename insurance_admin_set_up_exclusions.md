---
title: "Set Up Exclusions and Clauses"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_exclusions.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up Exclusions and Clauses

Set Up Exclusions and Clauses[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Exclusions and Clauses

To set up exclusions and clauses you use Constraint Builder to update the constraint model that defines the insurance product. From that model, you generate content text that you use to create specific clauses that can be automatically or manually added to quotes.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Lightning Experience</strong></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create rule models using Constraint Builder | Product Configuration Rules User |
| To create add clauses to products | Manage Product Catalog |

1.  Create the exclusion or clause.[](https://help.salesforce.com/s?language=en_US)
    1.  From the App Launcher, select Insurance Clause, then fill in the require fields.
    2.  The Code is whatever alphanumeric string you choose to reference the clause later when you create a rule model. For example vehicleUsage.
    3.  The Content Text is a combination of plain text and variables that are replaced with values based on your Context Definition mappings. An example for an auto insurance policy might be Use of the {{vehicleMake}} vehicle is categorized as {{usageType}} for {{userProfile}}.
    4.  Make sure the effective date is prior to the expiration date.
    5.  Set the Type to be either Exclusion or Clause.
    6.  Set the Creation Method of the exclusion or clause to either AutoAdded to automatically add it to quotes or Manual to required that it be added manually.
    7.  Save the clause.
2.  Add the Clauses component to your product pages.[](https://help.salesforce.com/s?language=en_US)
    1.  On each product page, select Setup then Edit Page.
    2.  Select the Details tab and in the right panel select Add Tab and choose Custom.
    3.  Name the new, custom tab Clauses.
    4.  In the left panel, select Components, search for Product Clauses, then drag that component onto the product page.
    5.  Save the page.
    6.  For more information about editing pages, see [https://help.salesforce.com/s/articleView?id=platform.lightning\_app\_builder\_customize\_lex\_pages\_add\_tabs.htm&language=en\_US](https://help.salesforce.com/s/articleView?id=platform.lightning_app_builder_customize_lex_pages_add_tabs.htm&language=en_US&type=5)
3.  Add the new clause to your product pages.[](https://help.salesforce.com/s?language=en_US)
    1.  From a product page, select Add Product Clause.
    2.  Select a product from the product hierarchy and click Next.
    3.  Select the clause you just created and click Save.
    4.  You should now see the clause displayed on the Clause tab of the product page.
4.  Configure the clause on the product page.[](https://help.salesforce.com/s?language=en_US)
    1.  On the product page, use the dropdown on the far right of the clause to select Configure.
    2.  Copy the contents of the Rule Name field and save it in a text editor. This field contains the rule key that you'll need later when working with Constraint Builder, for example Ex\_\_autoSilver\_\_auto\_\_vehicleUsage.
    3.  You may adjust the effective date and expiration date to shorten the period of the clause, but you can't extend the clause beyond the bounds set when you first defined it.
5.  Set up the rule model.[](https://help.salesforce.com/s?language=en_US)
    1.  Select Set up a rule model at the bottom of the clause configuration page. This takes you to a list of constraint models. If you don't have any constraint models yet, see[https://help.salesforce.com/s/articleView?id=ind.product\_configurator\_configuration\_rules.htm&language=en\_US](https://help.salesforce.com/s/articleView?id=ind.product_configurator_configuration_rules.htm&language=en_US&type=5) first.
    2.  Select a rule model to open Constraint Builder with that rule model.
    3.  In the Constraint Builder header in the upper left corner, select CML Editor.
    4.  Create a rule using the rule key you copied earlier when configuring the clause. For example, you might add the following to the section of a rule that defines coverage: `boolean Ex__autoSilver__auto__vehicleUsage = Year > 2020 && Auto_Value > 10000 && Auto_Value < 30000;`
    5.  See [https://help.salesforce.com/s/articleView?id=ind.product\_configurator\_use\_the\_cml\_editor.htm&language=en\_US](https://help.salesforce.com/s/articleView?id=ind.product_configurator_use_the_cml_editor.htm&language=en_US&type=5) for details on using the Constraint Modeling Language.
    6.  Save and activate the rule model.
6.  Map the variables you used in the Content Text.

Did this article solve your issue?

Let us know so we can improve!

YesNo