---
title: "Create Rating Procedures for Insurance Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_creating_rating_procedures_610011.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Rating Procedures for Insurance Products

Create Rating Procedures for Insurance Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Rating Procedures for Insurance Products

Before you start plugging rating information into rating procedures, analyze your existing rating system and the steps involved in pricing insurance products. Then translate these steps into lookup tables, expression sets, and Integration Procedures.

## Analyze Existing Rating Manuals and Procedures

Start with the total premium for a product. Figure out the formula used to derive the total premium, and then work backward step by step to deconstruct the calculations and lookups used to arrive at the amount. Identify the variables used in the formula and where each one comes from, for example:

-   Inputs.
    
-   Constants.
    
-   Tables, possibly with inputs and outputs.
    
-   Nested formulas.
    

Understand the "why" for each step in your rating system to be sure you're getting the right data into the formula. While you're analyzing the system, look for patterns and opportunities to simplify or consolidate tables.

## Create Rating Procedures by Using Business Rules Engine

Use Business Rules Engine components to create business rules that perform the lookups and calculations involved in rating insurance products and health plans. Depending on your business needs, you can also use an Integration Procedure as a rating procedure.

1.  Create lookup tables.
    
2.  Create expression sets.
    
    Before activating your expression set, run simulations with default and custom test input variables. Different decision matrices or sub expression versions called in an expression set version can have different start date time and end date time values. Test different versions by changing the Effective Date value. If the expression set doesn't work as expected, edit the elements and resimulate. When you're satisfied, activate the expression set.
    
3.  For the most complex ratings, or if you use a third-party rating engine, create Integration Procedures.
    

Note

If you have Integration Procedures from earlier releases, you can use calculation matrices and calculation procedures instead of lookup tables and expression sets.

## See Also

-   Business Rules Engine
    
-   [Simulate and Activate Your Expression Set Version](https://help.salesforce.com/s/articleView?id=ind.simulate_and_activate_the_expression_set.htm&language=en_US&type=5)
    
-   [Integration Procedure as Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedure_as_rating_procedure_610568.htm&language=en_US&type=5 "If you calculate ratings for multi-instance insurance products or health plans, or if you use a third-party rating engine, use an Integration Procedure as a rating procedure.")
    

## See Also

-   [Business Rules Engine](https://help.salesforce.com/s/articleView?id=ind.business_rules_engine.htm&language=en_US&type=5)
    
-   [Simulate and Activate Your Expression Set Version](https://help.salesforce.com/s/articleView?id=ind.simulate_and_activate_the_expression_set.htm&language=en_US&type=5)
    
-   [Integration Procedure as Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedure_as_rating_procedure_610568.htm&language=en_US&type=5 "If you calculate ratings for multi-instance insurance products or health plans, or if you use a third-party rating engine, use an Integration Procedure as a rating procedure.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo