---
title: "Assign a Pricing Procedure to a Product"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_pricing_procedure_for_quote.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Assign a Pricing Procedure to a Product

Assign a Pricing Procedure to a Product[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Assign a Pricing Procedure to a Product

To provide your customers with the most precise pricing experience, specify the pricing procedure that you want to use at the product level.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create and update procedure plan definitions: | 
Procedure Plan Access

AND

Salesforce Pricing Design Time User

 |

1.  From Setup, in the Quick Find box, enter Procedure Plan, and then select **Procedure Plan Definitions**.
2.  Click **New**.
3.  Enter a title and a developer name.
4.  Select **Insurance** as the process type.
5.  Find and select **Product (Product2)** as the primary object.
6.  As the context definition, select the extended context you created from **InsuranceContext**.
7.  Save the definition.
8.  Open the procedure plan definition. If necessary, set the context mapping to read and save data from a mapped object.
9.  In Procedure Plan Sections, click **Add**.
10.  Enter a name, and select **Pricing Procedure** as the section type. Make sure that **Standard** is selected, and then save your changes.
11.  Select **Rule-based** as the resolution type, and then click **Add Criteria**.
12.  Set the criteria for the rule-based pricing procedure.
     
     For example, to set InsuranceDefaultPricingProcedure as the pricing procedure to be used for a product called Auto Root, the pricing admin sets this criterion.
     
     | Resource | Operator | Output Value |
     | --- | --- | --- |
     | Product Name | Equals | Auto Root |
     
13.  Add as many criteria as you need for your pricing setup.
14.  Save your changes, and activate the definition of your procedure plan.

Did this article solve your issue?

Let us know so we can improve!

YesNo