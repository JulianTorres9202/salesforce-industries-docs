---
title: "Rating Procedure for Commercial Auto"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedure_for_commercial_auto_reference_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Rating Procedure for Commercial Auto

Rating Procedure for Commercial Auto[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Rating Procedure for Commercial Auto

To rate the Commercial Auto insurance product, we use this Integration procedure:

-   Type/SubType - Rating/CommercialAuto
    
-   Integration Procedure Name - CommercialAutoRating
    

Here's what the actual CommercialAutoRating Integration Procedure looks like:

While you'll create your own integration procedure to rate your auto insurance products, you can look at and test out the structure of this one to see how it works. You can model your own Integration Procedure on this one if it works for you.

The Integration Procedure comprises of `rateCommercialAuto` expression set action that rates vehicles by calling the `autoRateCommercialVehicles` expression set.

The following remote options are set:

[](https://help.salesforce.com/s?language=en_US)

-   Key: includeInputKeys
    
    Value: autoVehicle.instanceKey,location.instanceKey,productKey,parentProdKey
    
    What it does: This option specifies the keys to include from the input set into the output sets of the calculation results. These keys are later used to identify the correct set of calculation results by the aggByKey option as well as in the subsequent steps of this Integration Procedure.
    
-   Key: includeInputs
    
    Value: true
    
    What it does: Turns on the code that pulls the instance keys specified by the includeInputKeys option.
    
-   Key: aggByKey
    
    Value: autoVehicle.instanceKey
    
    What it does: Uses the autoVehicle.instance key InputKey in the calculation results sets to determine the sets to run aggregation steps on.
    

We expect that you'll create your own expression sets to rate vehicles for your auto insurance products. You can use `autoRateCommercialVehicles` as a model, and make changes to it so you can see how expression sets work.

[](https://help.salesforce.com/s?language=en_US)

1.  Does a matrix lookup on the value of the car.
    
2.  Does a matrix lookup on the car symbol.
    
3.  Does a matrix lookup on the year of the car.
    
4.  Does a matrix lookup to see if the car uses alternative fuel.
    
5.  Does a matrix lookup to see whether the car has stability controls.
    
6.  Does a matrix lookup to see whether the car has anti-theft protection.
    
7.  Does a matrix lookup to see whether the car has anti-lock brakes.
    
8.  Calculates the Bodily Injury & Property Damage.
    
9.  Calculates the Uninsured Motorist.
    
10.  Calculates the Medical payments.
     
11.  Calculates the CCD.
     
12.  Calculates the Collision.
     
13.  Does a matrix lookup for the Collision deductible.
     
14.  Does a matrix lookup for the Uninsured Motorist.
     
15.  Does a matrix lookup for the Medical payment limit.
     
16.  Does a matrix lookup for a Bodily Injury & Property Damage.
     
17.  Does a matrix lookup to get the CCD deductible.
     
18.  Calculates the Bodily Injury & Property Damage coverage premium.
     
19.  Calculates the premium for Uninsured Motorist coverage.
     
20.  Calculates the Medical payments premium.
     
21.  Calculates the premium for CCD coverage.
     
22.  Calculates the premium for Collision coverage.
     
23.  Calculates the premium for Rental Car coverage.
     
24.  Calculates the Commercial Auto premium.
     

[](https://help.salesforce.com/s?language=en_US)To learn how to work with expression sets, see [Expression Sets](https://help.salesforce.com/s/articleView?id=ind.expression_sets.htm&language=en_US&type=5).

[](https://help.salesforce.com/s?language=en_US)Note

Before activating your expression set, run simulations with default and custom test input variables. Different decision matrices or sub expression versions called in an expression set version can have different start date time and end date time values. Test different versions by changing the Effective Date value. If the expression set doesn't work as expected, edit the elements and resimulate. When you're satisfied, activate the expression set. For more information, see [Simulate and Activate Your Expression Set Version](https://help.salesforce.com/s/articleView?id=ind.simulate_and_activate_the_expression_set.htm&language=en_US&type=5).

`autoRateCommercialVehicles` includes an aggregation step that calculate aggregated premiums per vehicle. This step calculates the sum of all the Commercial Auto premiums calculated from each run of the calculation steps.

Did this article solve your issue?

Let us know so we can improve!

YesNo