---
title: "Multi Auto Rating Procedure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_procedure_511232.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multi Auto Rating Procedure

Multi Auto Rating Procedure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multi Auto Rating Procedure

A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.

[](https://help.salesforce.com/s?language=en_US)

This video shows you the steps and processes of the Multi Auto rating procedure:

[](https://help.salesforce.com/s?language=en_US)

Each insurer defines how they will calculate prices for their insurance products. This rating procedure provides one realistic example for calculating auto insurance product prices. You can use our example as a guide as you decide how to create your own auto insurance rating procedure.

[](https://help.salesforce.com/s?language=en_US)

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see Rating Procedures.

[](https://help.salesforce.com/s?language=en_US)

Here's how the Multi Auto rating procedure rates these things at the highest level:

[](https://help.salesforce.com/s?language=en_US)

## Integration Procedure for Multi Auto

To rate the Multi Auto insurance product, we use this Integration procedure:

-   Type: Auto
    
-   Subtype: MultiInstanceRating
    
-   Name: Auto+MultiDriver Rating
    

Here's what this Integration Procedure does, at a high level:

The Integration Procedure orchestrates the two major rating calculations--the driver calculations and then the vehicle calculations.

Here's what the actual Auto MultiInstanceRating Integration Procedure looks like:

While you'll create your own integration procedure to rate your auto insurance products, you can look at and test out the structure of this one to see how it works. You can model your own Integration Procedure on this one if it works for you.

Here's what component each step of the procedure uses, and what each step does:

1.  Calculation Action
    
    Rates the drivers by calling the calculation procedure.
    
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
        
        What it does: This value is passed in as an option to the InsProductService:getRatedProduct service by this Integration Procedure. This data is used to pull the correct versions of calculation procedures and matrices the Integration Procedure uses.
        
2.  List Action
    
    Merges the calculation results (rateDrivers:output:aggregationResults) for drivers from step 1 with the original input data (input\_1) from the input JSON. Matches the autoVehicle.instanceKey from the driver calculation output and merges the data.
    
3.  Calculation Action
    
    Rates the vehicles by calling the calculation procedure.
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Key: includeInputKeys
        
        Value: autoVehicle.instanceKey,productKey,parentProdKey
        
        What it does: This option specifies the keys to include from the input set into the output sets of the calculation results.
        
    -   Key: includeInputs
        
        Value: true
        
        What it does: Turns on the code that pulls the instance keys specified by the includeInputKeys option.
        
    -   Key: includeRawCalculationResult
        
        Value: true
        
        What it does: Appends the raw calculation results from this calculation procedure to the output JSON (as well as the parsed calculation results).
        
    -   Key: effectiveDate
        
        Value: %options:effectiveDate%
        
        What it does: This value is passed in as an option to the InsProductService:getRatedProduct service by this Integration Procedure. This data is used to pull the correct versions of calculation procedure and matrices the Integration Procedure uses.
        
4.  Response Action
    
    Returns the response for the calculation action in step 4. The **Send JSON Path** specified is standard, sending only the necessary node(s).
    

The Multi Auto rating procedure also uses calculation procedures to perform a series of calculations on matrix lookups and user-defined variables and constants. A calculation matrix is a table that looks up information using multiple input dimensions and returns the corresponding output value. The Multi Auto Integration Procedure calls these calculation procedures:

-   [autoRateDrivers](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_511353.htm&language=en_US&type=5 "This calculation procedure rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.")
    
    This calculation procedure rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.
    
-   [autoRateVehicles](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicles_511465.htm&language=en_US&type=5 "This calculation procedure rates all vehicles to be insured.")
    
    This calculation procedure rates all vehicles to be insured.
    

-   **[autoRateDrivers](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_511353.htm&language=en_US&type=5)**  
    This calculation procedure rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.
-   **[autoRateVehicles](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicles_511465.htm&language=en_US&type=5)**  
    This calculation procedure rates all vehicles to be insured.

Did this article solve your issue?

Let us know so we can improve!

YesNo