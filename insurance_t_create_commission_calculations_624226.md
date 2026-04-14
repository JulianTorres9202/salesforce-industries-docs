---
title: "Create Commission Calculations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_commission_calculations_624226.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Commission Calculations

Create Commission Calculations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Commission Calculations

Automate complex commission calculations with Decision Matrices, Expression Sets, and Integration Procedures. Your commission schedules either reference these calculations or specify flat amounts or fixed rates.

Note

You can also use Calculation Matrices and Calculation Procedures to automate commission calculations.

Choose the right tools for the job depending on the complexity of the calculation.

|  | 
Action

 | 

Result

 |
| --- | --- | --- |
| 

[Flat and tiered matrices](https://help.salesforce.com/s/articleView?id=ind.insurance_t_decision_matrices_for_commissions_624271.htm&language=en_US&type=5 "Decision Matrices give you a way to implement complex rules in a systematic, readable way. To calculate commissions based on something more complex than a fixed percentage rate, you start by setting up Decision Matrices.")

 | 

Take a unique input or set of inputs

 | 

Return a unique output or set of outputs

 |
| 

[Expression Sets](https://help.salesforce.com/s/articleView?id=ind.insurance_expression_sets_for_commissions_624353.htm&language=en_US&type=5 "Expression Sets give you the flexibility to perform multiple steps to arrive at a commission amount. You can incorporate a Decision Matrix lookup into an Expression Set.")

 | 

Look up values in matrices

Invoke multi-step calculations with conditional evaluations

Perform mathematical operations

 | 

Return calculated commission values

 |
| 

[Integration Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedures_for_commissions_624371.htm&language=en_US&type=5 "If a commission calculation requires data from multiple sources, use Integration Procedures to pull all the necessary data together. You can incorporate matrix lookups into an Integration Procedure, have the Integration Procedure use an Omnistudio Data Mapper to fetch data from another source, and then factor that data into the calculation.")

 | 

Look up values in matrices and external data sources

Invoke external integrations

Invoke multiple expression sets

Manage multiple layers of data transformations

 | 

[](https://help.salesforce.com/s?language=en_US)Return calculated commission values

 |

[](https://help.salesforce.com/s?language=en_US)

## What's Next

-   [Create Commission Schedules](https://help.salesforce.com/s/articleView?id=ind.insurance_t_create_commission_schedules_624454.htm&language=en_US&type=5 "Commission schedules define commission calculations and effective dates. You can create a bunch of commission schedules and have different ones in effect for different producers and insurance products, at different times.")
    

-   **[Decision Matrices for Commissions](https://help.salesforce.com/s/articleView?id=ind.insurance_t_decision_matrices_for_commissions_624271.htm&language=en_US&type=5)**  
    Decision Matrices give you a way to implement complex rules in a systematic, readable way. To calculate commissions based on something more complex than a fixed percentage rate, you start by setting up Decision Matrices.
-   **[Expression Sets for Commissions](https://help.salesforce.com/s/articleView?id=ind.insurance_expression_sets_for_commissions_624353.htm&language=en_US&type=5)**  
    Expression Sets give you the flexibility to perform multiple steps to arrive at a commission amount. You can incorporate a Decision Matrix lookup into an Expression Set.
-   **[Integration Procedures for Commissions](https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedures_for_commissions_624371.htm&language=en_US&type=5)**  
    If a commission calculation requires data from multiple sources, use Integration Procedures to pull all the necessary data together. You can incorporate matrix lookups into an Integration Procedure, have the Integration Procedure use an Omnistudio Data Mapper to fetch data from another source, and then factor that data into the calculation.

Did this article solve your issue?

Let us know so we can improve!

YesNo