---
title: "Update the Transaction Type to Use Standard Configurator"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_risk_engine.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Update the Transaction Type to Use Standard Configurator

Update the Transaction Type to Use Standard Configurator[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Update the Transaction Type to Use Standard Configurator

If you enabled Advanced Configurator but need existing quotes to run with Standard Configurator instead, create a Standard Configurator transaction type and update quotes to use it. Existing quotes then run with Standard Configurator rules, while new quotes use the default TPT you specify.

1.  Create a Standard Configurator TPT.
2.  For a small number of quotes, manually edit each quote and set the Transaction Type to the Standard Configurator TPT you created.
3.  For large number of quotes:
    1.  Export existing quotes to a .csv file using the following SOQL query: `SELECT Id, TransactionType FROM Quote`
        
        Apply filters to narrow results to the quotes you want to update.
        
    2.  In the exported CSV file, replace the values in the TransactionType column with the DeveloperName of your Standard Configurator TPT.
    3.  Use Workbench to bulk update Quote records with the CSV file. Use Async update if you’re working with large datasets.

[](https://help.salesforce.com/s?language=en_US)

## Update Procedure Plan Definition

Ensure quotes use the Standard Configurator by adding criteria for the new transaction processing type in the procedure plan.

1.  From Setup, in the Quick Find box, find and select **Procedure Plan Definitions**.
2.  Open the procedure plan definition that you've configured for Insurance.
3.  Click **Deactivate**.
4.  In the Quote-level Procedure Plan Sections, locate the pricing procedure section.
5.  Add a new condition to use the correct pricing procedure.
    
    | resource | operator | output value |
    | --- | --- | --- |
    | Label | Equals | Standard Configurator |
    
    In the condition, specify the DeveloperName of the Standard Configurator TPT.
    
6.  Save and activate your procedure plan definition.

-   Updated quotes continue to run with Standard Configurator rules.
-   New quotes run with the default TPT set in Revenue Settings. If no default TPT is set, new quotes default to Advanced Configurator.

Did this article solve your issue?

Let us know so we can improve!

YesNo