---
title: "Calculation Steps in a Rating Integration Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_calculation_steps_in_the_integration_procedure_610647.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Calculation Steps in a Rating Integration Procedure

Calculation Steps in a Rating Integration Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Calculation Steps in a Rating Integration Procedure

An Integration Procedure that rates an insurance or health product includes at least one Expression Set Action, or it includes a Remote Action that calls the third-party rating engine you use to rate products.

An Expression Set Action calls an existing expression set and passes it the input JSON so it can do its part to calculate the rating.

To make this work, set up the following Remote Properties:

-   **Remote Class**: namespace.PricingMatrixCalculationService
    
-   **Remote Method**: calculate
    
-   **Configuration Name**: calculationProcedureName
    
-   **Remote Option**
    
    -   **Key**: includeInputKeys
        
    -   **Value**: productKey,parentProdKey
        
-   **Remote Option**
    
    -   **Key**: includeInputs
        
    -   **Value**: true
        

[](https://help.salesforce.com/s?language=en_US)With these options and values, the expression set (or third-party calculation engine) can return the `productKey` and `parentProdKey` in the output.

Did this article solve your issue?

Let us know so we can improve!

YesNo