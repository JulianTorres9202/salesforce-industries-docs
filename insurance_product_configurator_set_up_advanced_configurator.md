---
title: "Set Up Constraint Rules Engine"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_product_configurator_set_up_advanced_configurator.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Constraint Rules Engine

Set Up Constraint Rules Engine[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Constraint Rules Engine

Set up the Constraint Rules Engine rule engine by creating the ConstraintEngineNodeStatus custom field on Quote Line Item object, updating the InsuranceContext context definition to map the field, and adjusting your procedure plan definition so that Insurance quotes use Constraint Rules Engine.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Developer</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions of Revenue Cloud where Product Configurator is enabled</td></tr></tbody></table>

Permission Set
| Permission Set Name | Description |
| --- | --- |
| Product Configuration Constraints Designer | Create and manage constraint types and rules in Configurator with Constraint Rules Engine. |

[](https://help.salesforce.com/s?language=en_US)

## Create the ConstraintEngineNodeStatus Custom Field

Before your rule designers can create advanced configuration rules and sales reps can use them, you must create the ConstraintEngineNodeStatus custom field on the Quote Line Item object. Constraint Rules Engine uses the fields to store data for internal processing.

1.  From the object management settings for Quote Line Item, go to Fields & Relationships.
2.  Click **New**.
3.  Select **Text Area (Long)**, and then click **Next**.
4.  Enter Constraint Engine Node Status as the field label.
5.  Enter 5000 as the length.
6.  Enter ConstraintEngineNodeStatus as the field name.
7.  Click **Next**.
8.  For the profiles whose users use Constraint Rules Engine, make sure that the Read-Only option is deselected.
    
    Note For Customer Community and Partner Community users to run constraints, give these profiles also access to this field. Select the Visible option and deselect the Read-Only option for the profiles.
    
9.  Click **Next**.
10.  Deselect the page layouts, and save your changes.

[](https://help.salesforce.com/s?language=en_US)

## Update the InsuranceContext Context Definition

After you create the ConstraintEngineNodeStatus field, update your extended InsuranceContext context definition ​​to use the field. If you don’t have the extended context definition, extend InsuranceContext before you add the attribute.

Note Make sure to use the extended InsuranceContext context definition that is configured for your default pricing procedure.

1.  From Setup, in the Quick Find box, enter Context Service, and then select **Context Definitions**.
2.  [Edit your extended InsuranceContext context definition.](https://help.salesforce.com/s/articleView?id=ind.context_service_view_edit_saved_context_definitions.htm&language=en_US&type=5)
3.  Select the SalesTransactionItem node under SalesTransaction.
4.  [Add the ConstraintEngineNodeStatus attribute](https://help.salesforce.com/s/articleView?id=ind.context_service_create_context_definitions.htm&language=en_US&type=5) to the InsuranceItem node with INPUTOUTPUT as the type and STRING as the data type.
5.  Click **Next**.
6.  Select the SalesTransactionItem node under SalesTransaction.
7.  Add a new tag ConstraintEngineNodeStatus\_\_c for ConstraintEngineNodeStatus\_\_c.
8.  Save your changes.
9.  Adjust the InsuranceContext context definition mapping to include the custom field.
    1.  Select the Map Data tab and then edit QuoteEntitiesMapping.
10.  In the Map Data tab, make these updates.
     1.  Edit QuoteEntitiesMapping and then map the ConstraintEngineNodeStatus attribute under SalesTransactionItem to the ConstraintEngineNodeStatus\_\_c field on the QuoteLineItem object.
     2.  In QuoteEntitiesMapping, review the context mappings and make sure that the TransactionType attribute on the SalesTransaction node is mapped to the TransactionType field on the Quote object.
11.  Save your changes and activate your context definition.

[](https://help.salesforce.com/s?language=en_US)

## Update Procedure Plan Definition

Define rule-based criteria for the Advanced Configurator transaction processing type in your existing procedure plan definition for insurance.

Make sure you've already [set up a procedure plan definition](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_pricing_procedure_for_product.htm&language=en_US&type=5) with:

-   Process Type: Insurance
-   Primary Object: Transaction Processing Type
-   At least one Pricing Procedure section
-   Rule-based resolution

1.  From Setup, in the Quick Find box, find and select **Procedure Plan Definitions**.
2.  Open the procedure plan definition you've configured for Insurance.
3.  In the Procedure Plan Sections area, locate the pricing procedure section.
4.  Confirm that the Resolution Type is set to Rule-Based.
5.  Add a new condition to support the Advanced Configurator transaction processing type:
    
    | resource | operator | output value |
    | --- | --- | --- |
    | Label | Equals | Advanced Configurator |
    
    In the condition, specify the DeveloperName of the Advanced Configurator TPT.
    
6.  Save and activate your procedure plan definition.

[](https://help.salesforce.com/s?language=en_US)

## Enable Constraint Rules Engine

Enable rule designers to create advanced configuration rules and constraints, and help sales reps run the rules for transactions (quotes).

1.  From Setup, in the Quick find box, enter Revenue Settings, and then select **Revenue Settings**.
2.  Turn on Set Up Configuration Rules and Constraints with Constraint Rules Engine.
    
    When you enable Constraint Rules Engine, AdvancedConfigurator is the default engine for transaction types in your org.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo