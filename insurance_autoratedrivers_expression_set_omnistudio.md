---
title: "autoRateDrivers Expression Set"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_expression_set_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# autoRateDrivers Expression Set

autoRateDrivers Expression Set[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# autoRateDrivers Expression Set

This expression set rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.

Here's what the autoRateDrivers calculation looks like in detail:

Some drivers are rated more than once by this expression set.

This expression set includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific lookup table matrices.

We expect that you'll create your own expression set to rate drivers for your auto insurance products. You can use autoRateDrivers as a model, and make changes to it so you can see how expression set work.

To learn more about creating and editing expression set in general, see [Build your Expression Set](https://help.salesforce.com/s/articleView?id=sf.build_exp_set.htm&language=en_US&type=5).

The meat of the expression set is its calculation steps. Here's what each step of the autoRateDrivers expression set does:

1.  Calculates the driver's age.
    
2.  Calculates the driver's years of driving experience.
    
3.  Calculates the number of points the driver has on their license.
    
4.  Does a Matrix Lookup to determine whether the driver is a good student.
    
5.  Does a Matrix Lookup to determine whether the driver is a safe driver.
    
6.  Does a Matrix Lookup to get values for the driver class (demographic info).
    
7.  Does a Matrix Lookup to get values based on the driver's points.
    
8.  Does a Matrix Lookup to get values based on whether the driver is a safe driver.
    
9.  Calculates a value for the driver's bodily injury & property damage coverage.
    
10.  Calculates a value for the driver's uninsured motorist coverage.
     
11.  Calculates a value for the driver's medical payment coverage.
     
12.  Calculates a value for the driver's comprehensive coverage.
     
13.  Calculates a value for the driver's collision coverage.
     

-   **[Aggregation Steps for autoRateDrivers](https://help.salesforce.com/s/articleView?id=ind.insurance_aggregation_steps_for_autoratedrivers_with_omnistudio.htm&language=en_US&type=5)**  
    autoRateDrivers includes aggregation steps that calculate aggregated premiums per driver for specific coverages:
-   **[autoRateDrivers Lookup Tables](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_lookup_tables_omnistudio.htm&language=en_US&type=5)**  
    The autoRateDrivers expression set uses lookup tables to identify drivers.

Did this article solve your issue?

Let us know so we can improve!

YesNo