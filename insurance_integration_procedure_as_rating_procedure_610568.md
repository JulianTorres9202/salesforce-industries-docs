---
title: "Integration Procedure as Rating Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedure_as_rating_procedure_610568.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Integration Procedure as Rating Procedure

Integration Procedure as Rating Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Integration Procedure as Rating Procedure

If you calculate ratings for multi-instance insurance products or health plans, or if you use a third-party rating engine, use an Integration Procedure as a rating procedure.

For less complex products and plans, an expression set can function as your rating procedure instead. If you're not sure whether to use an Integration Procedure, see [Rating Procedure Best Practices](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_best_practices_610890.htm&language=en_US&type=5 "Setting up your first rating procedure? These best practices help you optimize your rating implementations.").

Integration Procedures can include multiple steps and multiple expression sets. Manage the data structure yourself using Integration Procedure tools.

Note

If you have Integration Procedures from earlier releases, you can use calculation matrices and calculation procedures instead of lookup tables and expression sets.

When you're working with rating Integration Procedures, the two most important things to keep track of are:

-   Input JSON structure.
    
    Examine this structure so you understand what's coming into your Integration Procedure.
    
-   Output JSON structure.
    
    Set up an output structure similar to that of a expression set's output that can be parsed by the `InsProductService:getRatedProducts` or `InsProductService:repriceProduct` service and mapped to the correct values in the product JSON.
    

Your Integration Procedure can also use a merge List Action to make multi-instance ratings possible, and can transform data with Omnistudio Data Mappers.

After you create your Integration Procedure, use the Simulator on the Integration Procedure Designer to test it. Enter the same data you used to test expression sets called by this Integration Procedure. The Integration Procedure simulation result should conform to `PricingCalculationService.CalculationProcedureResults`.

When you go on to test your rating procedure on a product, keep in mind that Integration Procedures don't work the same way on the product simulator as expression sets do.

Before you begin:

-   Consider using an expression set instead of an Integration Procedure. Integration Procedures can use more system resources, so use them only if the calculation is too complex for expression sets.
    
-   Create a product model.
    
-   Create all lookup tables required for this rating.
    
-   Create all expression sets required for this rating.
    

-   **[Required Input in a Rating Integration Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_required_input_610609.htm&language=en_US&type=5)**  
    Each input JSON node in a rating Integration Procedure must include `parentProdKey` and `productKey`. These two keys carry over as input to the expression sets called by this Integration Procedure.
-   **[Calculation Steps in a Rating Integration Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_calculation_steps_in_the_integration_procedure_610647.htm&language=en_US&type=5)**  
    An Integration Procedure that rates an insurance or health product includes at least one Expression Set Action, or it includes a Remote Action that calls the third-party rating engine you use to rate products.
-   **[Data Transforms in a Rating Integration Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_data_transforms_610698.htm&language=en_US&type=5)**  
    Transform data if necessary based on the format of the input JSON and the format of the results of the expression set or external rating engine.
-   **[Required Output in a Rating Integration Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_required_output_610709.htm&language=en_US&type=5)**  
    The output of your rating Integration Procedure needs to follow the same structure as expression set output.
-   **[Services that Call Rating Integration Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_services_that_call_rating_integration_procedures_610740.htm&language=en_US&type=5)**  
    When you create a rating Integration Procedure, think about what services call it. The services inform how you create the Integration Procedure and the structure of input and output data.
-   **[Integration Procedure for an Auto Insurance Product Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedure_for_auto_610774.htm&language=en_US&type=5)**  
    The product model underpins all the business processes used in a line of business. Services that price insurance products pull data from the product model, perform rating procedure calculations using that data, and then insert coverage and premium prices into the product model.

Did this article solve your issue?

Let us know so we can improve!

YesNo