---
title: "Set up Insurance Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_quoting.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set up Insurance Quoting

Set up Insurance Quoting

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Set up Insurance Quoting

Before you can start quoting, there are a few setup tasks that you must complete.

[](https://help.salesforce.com/s?language=en_US)

## Configure Pricing Procedures for Insurance Quotes

Calculate prices for insurance quotes by setting up context definitions, transaction types, and procedure plan definitions. You can configure pricing procedures at both the product level and the quote level. A quote-level pricing procedure is required, and product-level pricing procedures are optional.

[](https://help.salesforce.com/s?language=en_US)

### Pricing Overview

Learn how Insurance processes pricing procedures for individual products and for the quote as a whole.

A quote can contain one or more root products. For example, a quote that contains both an Auto Insurance root product and a Home Insurance root product can use separate pricing procedures for each product and an additional pricing procedure at the quote level for calculations that evaluate both products together.

If a quote contains only one root product, you may not need a product-level pricing procedure. The quote-level pricing procedure is often sufficient for single-product quotes.

During rating, product-level pricing procedures run first when they match the quote’s root products, and the quote-level pricing procedure runs afterward. This sequence applies pricing logic to individual products first and then evaluates pricing across the full quote.

You must save the quote at least once before it can reference its quote-level pricing procedure.

[](https://help.salesforce.com/s?language=en_US)

### Assign a Specific Pricing Procedure to Quotes (Required)

To provide your customers with the most precise pricing experience, specify the pricing procedure that you want to use at the quote level.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Revenue Cloud where Salesforce Pricing is enabled</td></tr></tbody></table>

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
5.  Select **Transaction Processing Type** as the primary object.
6.  Enter the context definition name. This is the developer name of the context definition that is extended from InsuranceContext. For example, InsuranceContext.
7.  Save the definition.
8.  Open the new procedure plan defintion.
9.  Select **QuoteEntitiesMapping** for both read and save context mappings. If your org uses a custom mapping that extends QuoteEntitiesMapping, select that mapping instead.
10.  In Procedure Plan Sections, click **Add**.
11.  Enter a name, and select **Pricing Procedure** as the section type. Make sure that **Standard** is selected, and then save your changes.
12.  Select **Rule-based** as the resolution type, and then click **Add Criteria**.
13.  Set the criteria for the rule-based pricing procedure.
14.  Add as many criteria as you need for your pricing setup.
     
     For example, to set InsuranceDefaultPricingProcedure as the pricing procedure to be used for all quotes of Auto Transaction Type, the pricing admin can set this criterion:
     
     | Resource | Operator | Output Value |
     | --- | --- | --- |
     | Label | Equals | Auto Transaction Type |
     
15.  Select your pricing procedure.
16.  Save your changes, and activate the procedure plan definition.

[](https://help.salesforce.com/s?language=en_US)

### Create a Product-Level Procedure Plan Definition (Optional)

Create a product-level pricing procedure that applies to a specific root product.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Revenue Cloud where Salesforce Pricing is enabled</td></tr></tbody></table>

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
4.  Enter these values:
    
    -   Select **Insurance** as the process type.
    -   Select **Product** as the primary object.
    -   Enter the context definition name. This is the developer name of the context definition that is extended from InsuranceContext. For example, InsuranceContext.
    
5.  Save the definition.
6.  Open the new procedure plan defintion.
7.  Select **QuoteEntitiesMapping** for both read and save context mappings. If your org uses a custom mapping that extends QuoteEntitiesMapping, select that mapping instead.
8.  In Procedure Plan Sections, click **Add**.
9.  Enter a name, and select **Pricing Procedure** as the section type. Make sure that **Standard** is selected, and then save your changes.
10.  Save your changes.
11.  Select **Rule-based** as the resolution type, and then click **Add Criteria**.
12.  Add as many criteria as you need for your pricing setup.
     
     For example, to set InsuranceDefaultPricingProcedure as the pricing procedure to be used for a product called Auto Root, the pricing admin sets this criterion.
     
     | Resource | Operator | Output Value |
     | --- | --- | --- |
     | Label | Equals | Auto Root |
     
13.  Select your pricing procedure.
14.  Save your changes, and activate the procedure plan definition.

[](https://help.salesforce.com/s?language=en_US)

## Define Transaction Processing Types

Create the transaction processing type records that quotes use during pricing.

Use the REST api via Salesforce workbench or other REST clients to create the Transaction Processing Type.

URL / Endpoint: /services/data/v63.0/tooling/sobjects/TransactionProcessingType

Method: POST

Payload:

```
{ 
        "SaveType": "Standard", 
        "Description": "Save type for Auto transactions",
        "DeveloperName": "AutoTransactionType",
        "MasterLabel": "Auto Transaction Type",
        "RuleEngine": "StandardConfigurator" 
        }
```

Note Set the developer name to match the value you specified in the procedure plan criteria.

[](https://help.salesforce.com/s?language=en_US)

## Update the Quote Page Layout

To make the Transaction Type field available to your users, add the field to the Quote page layout.

1.  From Setup, open Object Manager, and select Quote.
2.  Open Page Layouts.
3.  Edit the layout you want to update.
4.  Add the Transaction Type field to the layout.
5.  Save your changes.

#### See Also

-   [Customize Pricing For Different Types of Transactions](https://help.salesforce.com/s/articleView?id=ind.qocal_customize_pricing_for_different_types_of_transactions.htm&language=en_US&type=5)
-   [Procedure Plan Framework](https://help.salesforce.com/s/articleView?id=ind.pricing_procedure_plan_framework.htm&language=en_US&type=5)
-   [Create a Custom Procedure Plan Definition](https://help.salesforce.com/s/articleView?id=ind.pricing_create_a_custom_procedure_plan_definition&language=en_US&type=5)
-   [Page Layouts](https://help.salesforce.com/s/articleView?id=platform.customize_layout.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

## Assign the Transaction Type to the Quote

Select the transaction type a quote uses during pricing. The quote uses the transaction type to lookup and apply the pricing procedure.

1.  Open a quote.
2.  Select a value in Transaction Type.
3.  Save your changes.

[](https://help.salesforce.com/s?language=en_US)

## Troubleshoot Pricing Procedure Errors

Identify and resolve pricing errors when you define and run pricing procedures at the quote level and root product level. Use this section after you complete the required setup for procedure plans, context definitions, context mappings, and transaction types.

### Error: No Quote level pricing procedure has been defined

-   Ensure that at least one pricing procedure plan is defined.
-   Confirm that the pricing procedure plan is active.
-   Verify that the pricing procedure plan Process Type is set to **Insurance**.
-   Confirm that the condition resource matches the resource used as the output value. For example, if the condition resource is product code, the output value must also be a product code, not a product name.
-   Verify that the condition output value is correct and matches the expected value.
-   Ensure that a Transaction Type is assigned to the quote.
-   Verify that the Transaction Type exists in the context and is correctly mapped in the context mapping.

### Error: Ensure that this procedure has at least one active version.

-   Ensure the pricing procedure has at least one active version.
-   Ensure the quote start date falls within the effective date range of the active pricing procedure version.

Did this article solve your issue?

Let us know so we can improve!

YesNo