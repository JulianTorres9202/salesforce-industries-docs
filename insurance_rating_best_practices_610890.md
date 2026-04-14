---
title: "Rating Procedure Best Practices"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rating_best_practices_610890.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Rating Procedure Best Practices

Rating Procedure Best Practices[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Rating Procedure Best Practices

Setting up your first rating procedure? These best practices help you optimize your rating implementations.

[](https://help.salesforce.com/s?language=en_US)

## Use an Expression Set for Less Complex Rating Procedures

Integration Procedures are ideal for creating complex aggregated ratings across multiple dimensions. Use an Integration Procedure if:

-   You're rating a multi-instance product that requires more than one expression set to complete the rating
-   You use a third-party rating engine to rate products

For less complex products, an expression set works well. Using Integration procedures when they're not necessary can create overhead that leads to sub-optimal performance. Performance issues can slow users down as they go through quote-to-bind flows.

Note If you have Integration Procedures from earlier releases, you can use calculation matrices and calculation procedures instead of lookup tables and expression sets.

Expression sets are optimized to rate products quickly. Before you start building Integration Procedures for your ratings, take advantage of all the functionality expression sets have to offer. Expression sets take multiple sets of inputs, do multiple table lookups, perform dozens of complex calculation steps, and aggregate results.

Note If an aggregation step is used in an expression set or calculation procedure, the aggregated output must be unique and not match the name of any calculation step.

When multiple input sets go into an expression set, the results of table lookups for the first input set are cached. The expression set runs faster by using the cached results for each subsequent input set.

[](https://help.salesforce.com/s?language=en_US)

## Run the Simulator for the Rating Procedure, Product Spec, and OmniScript

The best way to prevent and diagnose rating errors is to use the Simulators at each step of the rating process, starting from the bottom up.

1.  Expression Set
    
    Enter sample data into the expression set Simulator. If simulating the final step doesn't result in the correct coverage premium prices, simulate all steps and examine each step, adjusting until the expression set works correctly.
    
2.  Integration Procedure
    
    If you use an Integration Procedure as your rating procedure, enter the same sample data you used in the expression set into the preview for the Integration Procedure and examine the output to be sure that the rating calculates coverage premium prices correctly.
    
3.  Product Spec
    
    After you've added all input and output variables, the instance total premium formula, and the product total premium formula to the root product Simulate tab, add the same sample data you used for the rating procedure.
    
4.  OmniScript with Rating Services
    
    In the OmniScript Preview pane, enter the same sample data you used for the rating procedures and the product spec. Run the preview, and check to make sure that at the rating and repricing steps the coverage, instance, and total premiums are calculated correctly.
    

## See Also

[Simulate and Activate Your Expression Set Version](https://help.salesforce.com/s/articleView?id=ind.simulate_and_activate_the_expression_set.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo