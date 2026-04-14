---
title: "Integration Procedure for Multi Auto"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedure_for_multi_auto_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Integration Procedure for Multi Auto

Integration Procedure for Multi Auto[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Integration Procedure for Multi Auto

To rate the Multi Auto insurance product, we use this Integration procedure:

-   Type: Auto
    
-   Subtype: MultiInstanceRating
    
-   Name: Auto+MultiDriver Rating
    

Here's what this Integration Procedure does, at a high level:

The Integration Procedure orchestrates the two major rating calculations--the driver calculations and then the vehicle calculations.

Here's what the actual Auto MultiInstanceRating Integration Procedure looks like:

While you'll create your own integration procedure to rate your auto insurance products, you can look at and test out the structure of this one to see how it works. You can model your own Integration Procedure on this one if it works for you.

Here's what component each step of the procedure uses, and what each step does:

1.  Expression Set Action - rateDrivers
    
    Rates the drivers by calling the [autoRateDrivers expression sets](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_expression_set_omnistudio.htm&language=en_US&type=5 "This expression set rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.").
    
    The following remote options are set:
    
    -   Key: includeInputKeys
        
        Value: autoVehicle.instanceKey,autoDriver.instanceKey
        
        What it does: This option specifies the keys to include from the input set into the output sets of the calculation results. These keys are later used to identify the correct set of calculation results by the aggByKey option as well as in the subsequent steps of this Integration Procedure.
        
    -   Key: includeInputs
        
        Value: true
        
        What it does: Turns on the code that pulls the instance keys specified by the includeInputKeys option.
        
    -   Key: aggByKey
        
        Value: autoVehicle.instanceKey
        
        What it does: Uses the autoVehicle.instance key InputKey in the calculation results sets to determine the sets to run aggregation steps on.
        
    -   Key: effectiveDate
        
        Value: %options:effectiveDate%
        
        What it does: This value is passed in as an option to the InsProductService:getRatedProduct service by this Integration Procedure. This data is used to pull the correct versions of expression sets and lookup tables that the Integration Procedure uses.
        
2.  List Action - mergeDriverFactorsVehicles
    
    Merges the calculation results (rateDrivers:output:aggregationResults) for drivers from step 1 with the original input data (input\_1) from the input JSON. Matches the autoVehicle.instanceKey from the driver calculation output and merges the data.
    
3.  Expression Set Action - rateVehicle
    
    Rates the vehicles by calling the [autoRateVehicles expression sets](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicles_expression_set_omnistudio.htm&language=en_US&type=5 "This expression set rates all vehicles to be insured.").
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Key: includeInputKeys
        
        Value: autoVehicle.instanceKey,productKey,parentProdKey
        
        What it does: This option specifies the keys to include from the input set into the output sets of the calculation results.
        
    -   Key: includeInputs
        
        Value: true
        
        What it does: Turns on the code that pulls the instance keys specified by the includeInputKeys option.
        
    -   Key: includeRawCalculationResult
        
        Value: true
        
        What it does: Appends the raw calculation results from this expression set to the output JSON (as well as the parsed calculation results).
        
    -   Key: effectiveDate
        
        Value: %options:effectiveDate%
        
        What it does: This value is passed in as an option to the InsProductService:getRatedProduct service by this Integration Procedure. This data is used to pull the correct versions of expression sets and lookup tables that the Integration Procedure uses.
        
4.  Response Action
    
    Returns the response for the calculation action in step 4. The **Send JSON Path** specified is standard, sending only the necessary node(s).
    

The Multi Auto rating procedure also uses expression sets to perform a series of calculations on matrix lookups and user-defined variables and constants. A lookup table looks up for information using multiple input dimensions and returns the corresponding output value.

[](https://help.salesforce.com/s?language=en_US)Note

Before activating your expression set, run simulations with default and custom test input variables. Different decision matrices or sub expression versions called in an expression set version can have different start date time and end date time values. Test different versions by changing the Effective Date value. If the expression set doesn't work as expected, edit the elements and resimulate. When you're satisfied, activate the expression set. For more information, see [Simulate and Activate Your Expression Set Version](https://help.salesforce.com/s/articleView?id=ind.simulate_and_activate_the_expression_set.htm&language=en_US&type=5).

For more information on setting up Business Rule Engine, see [Business Rule Engine](https://help.salesforce.com/s/articleView?id=ind.business_rules_engine.htm&language=en_US&type=5).

The Multi Auto Integration Procedure calls these expression sets:

-   [autoRateDrivers](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_expression_set_omnistudio.htm&language=en_US&type=5 "This expression set rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.")
    
    This expression set rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.
    
-   [autoRateVehicles](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicles_expression_set_omnistudio.htm&language=en_US&type=5 "This expression set rates all vehicles to be insured.")
    
    This expression set rates all vehicles to be insured.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo