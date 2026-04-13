---
title: "Specify Which Rule Engine to Use"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_specify_rule_engine.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Specify Which Rule Engine to Use

Specify Which Rule Engine to Use[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Specify Which Rule Engine to Use

Use the Transaction Type field in a quote to specify the rule engine to use for validating product configurations and executing configuration rules and constraints. Create Transaction Processing Type records based on your requirements, and then specify the default rule engine on the Revenue Settings page to validate product configurations and execute rules and constraints.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Developer</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions of Revenue Cloud where Product Configurator is enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create transaction processing type records and to select a default transaction processing type: | 
Customize Application

AND

View Setup and Configuration

 |

Note While Business Rules Engine and Constraint Rules Engine can be enabled in the org at the same time, it's not recommended to change the Transaction Processing Type after quote creation. Switching between transaction types mapped to different rule engines may result in inconsistenties during rule execution.

-   **[Update the Transaction Type to Use Standard Configurator](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_risk_engine.htm&language=en_US&type=5)**  
    If you enabled Advanced Configurator but need existing quotes to run with Standard Configurator instead, create a Standard Configurator transaction type and update quotes to use it. Existing quotes then run with Standard Configurator rules, while new quotes use the default TPT you specify.

[](https://help.salesforce.com/s?language=en_US)

## Create Transaction Type Records

Create Transaction Processing Type records based on the rule engine that you want to use.

-   Before you create a Transaction Processing Type record, make sure that the [Configure Products at Runtime setting is turned on](https://help.salesforce.com/s/articleView?id=ind.product_configurator_enable_product_configurator.htm&language=en_US&type=5).
-   Your org should have a Transaction Processing Type (TPT) that is not using Advanced Configurator. To use Advanced Configurator, create a new TPT and set its rule engine to AdvancedConfigurator.

-   If only Constraint Rules Engine (the Set Up Configuration Rules and Constraints with Constraint Rules Engine setting) is enabled, Product Configurator uses Constraint Rules Engine to run configuration rules.
-   If only Business Rules Engine (the Set Up Configuration Rules with Business Rules Engine setting) is enabled, Product Configurator uses Business Rules Engine only if StandardConfigurator is the rule engine specified in the associated Transaction Processing Type record. If the Transaction Type field on quotes and orders or the Rule Engine field on the Transaction Processing Type record is blank, Product Configurator doesn't run any configuration rules.
-   If both rules engines are enabled, Product Configurator uses Business Rules Engine only if StandardConfigurator is the rules engine specified in the associated Transaction Processing Type record. Else, it uses Constraint Rules Engine.

1.  From Setup, in the Quick Find box, enter Revenue Settings, and then select **Revenue Settings**.
2.  Turn on Transaction processing for quotes.
    
    To learn how the Transaction processing for quotes setting works in Transaction Management, see [Configure Transaction Management Settings](https://help.salesforce.com/s/articleView?id=ind.qocal_turn_on_quote_and_order_capture.htm&language=en_US&type=5).
    
3.  Use TransactionProcessingType Tooling API to create a Transaction Processing Type record and specify the rule engine.
    
    Sales reps can’t see the fields in Transaction Processing Type records. If necessary, append the name of the rule engine to the Transaction Processing Type record name.
    
4.  If necessary, [modify the field access settings](https://help.salesforce.com/s/articleView?id=platform.modifying_field_access_settings.htm&language=en_US&type=5) of the Transaction Type field on the Quote objects to provide view access to the necessary profiles.

Example

Create transaction type records with these details.

[](https://help.salesforce.com/s?language=en_US)

-   URI: /services/data/v63.0/tooling/sobjects/TransactionProcessingType
-   Request Type: POST
-   Payload:
    
    [](https://help.salesforce.com/s?language=en_US)`{ "SaveType": "Standard",  "Description": "<Enter a description>",  "DeveloperName": "<Enter a developer name>",  "MasterLabel": "<Enter a label>",  "RuleEngine": "<AdvancedConfigurator or StandardConfigurator>"}` 
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    -   Enter the values for Description, DeveloperName, MasterLabel, and RuleEngine.
    -   If you want to switch back to Standard Configurator after enabling Advanced Configurator in Revenue Settings, make sure the rule engine specified in the associated TPT record is set to StandardConfigurator.
    

[](https://help.salesforce.com/s?language=en_US)

## Select the Default Rule Engine

Select a default Transaction Processing Record, containing the rule engine type, to be assigned to quotes.

1.  From Setup, in the Quick Find box, enter Revenue Settings, and then select **Revenue Settings**.
2.  In the ​​Transaction processing for quotes section, select the default transaction type.

When users create quotes, the Transaction Type field is automatically populated with the default Transaction Processing Type record. Admins and sales reps with the appropriate permissions can modify the Transaction Type field on quotes and orders.

When the Transaction Type field is blank and no default transaction type is defined:

-   If the Set Up Advanced Configuration Rules and Constraints setting is turned on, the Advanced Configurator engine runs the configuration rules.
-   If the setting isn’t turned on, configuration rules aren't run.

Did this article solve your issue?

Let us know so we can improve!

YesNo