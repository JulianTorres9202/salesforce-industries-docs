---
title: "autoRateDrivers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_autoratedrivers_511353.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# autoRateDrivers

autoRateDrivers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# autoRateDrivers

This calculation procedure rates all drivers to be insured on a per-vehicle basis. That is, it rates each driver attached to each vehicle.

[](https://help.salesforce.com/s?language=en_US)

Here's what the autoRateDrivers calculation looks like in detail:

Some drivers will be rated more than once by this calculation procedure.

[](https://help.salesforce.com/s?language=en_US)

This calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.

We expect that you'll create your own calculation procedure to rate drivers for your auto insurance products. You can use autoRateDrivers as a model, and make changes to it so you can see how calculation procedures work.

The meat of the calculation procedure is its calculation steps. Here's what each step of the autoRateDrivers calculation procedure does:

[](https://help.salesforce.com/s?language=en_US)

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
     

[](https://help.salesforce.com/s?language=en_US)

## Aggregation Steps

autoRateDrivers includes aggregation steps that calculate aggregated premiums per driver for specific coverages:

1.  Calculates the rated driver Bodily Injury & Property Damage (BIPD) by averaging the driverBIPD outputs from each run of the calculation steps.
    
    If one driver has been rated twice because they're in two driver+vehicle sets, this step averages their BIPD rating and returns one value.
    
    Note
    
    This works the same way and for the same reason for all the following aggregation steps.
    
2.  Calculates the rated driver Uninsured Motorist (UM) by averaging driverUM outputs from each run of the calculation steps.
    
3.  Calculates the rated driver Medical payments (MED) by averaging driverMED outputs from each run of the calculation steps.
    
4.  Calculates the rated driver comprehensive (CCD) by averaging driverCCD outputs from each run of the calculation steps.
    
5.  Calculates the rated driver Collision (COLL) by averaging driverCOLL outputs from each run of the calculation steps.
    

[](https://help.salesforce.com/s?language=en_US)

## Calculation Matrices

The following calculation matrices are called by autoRateDrivers:

| 
Calculation Matrix Name

 | 

Description

 |
| --- | --- |
| 

autoDriverClass

 | 

Handles a combination of characteristics of drivers as entered by customers:

-   Years experience
    
-   Gender
    
-   Marital Status
    
-   Good Student
    

Takes inputs that vary per characteristic. These inputs are outputs of other calculation matrices. Returns percentage outputs.

 |
| 

autoDriverGoodStudent

 | 

Handles the GPA of a student driver entered by a customer.

Takes a numeric value. Returns a Y or N value.

 |
| 

autoDriverPoints

 | 

Handles the points on the driver's record, entered by a customer.

Takes a numeric input. Returns a number of percentage outputs.

 |
| 

autoDriverSafe

 | 

Handles user data about whether a driver is rated as safe.

Takes a Y or N input. Returns a number of percentage outputs.

 |
| 

autoSafeDriver

 | 

Handles data about a driver's safety record.

Takes a numeric input. Returns a Y or N output.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo