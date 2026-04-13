---
title: "autoRateVehicles Expression Set"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicles_expression_set_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# autoRateVehicles Expression Set

autoRateVehicles Expression Set[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# autoRateVehicles Expression Set

This expression set rates all vehicles to be insured.

It includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific lookup table matrices.

We expect that you'll create your own expression set to rate vehicles for your auto insurance products. You can use autoRateVehicles as a model, and make changes to it so you can see how expression sets work.

[](https://help.salesforce.com/s?language=en_US)To learn more about creating and editing expression set in general, see [Build your Expression Set](https://help.salesforce.com/s/articleView?id=sf.build_exp_set.htm&language=en_US&type=5).

The meat of the expression set is its calculation steps. Here's what each step of the autoRateVehicles expression set does:

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
     

-   **[autoRateVehiclesLookup Tables](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratevehicleslookup_tables_omnistudio.htm&language=en_US&type=5)**  
    The autoRateVehiclesLookup expression set uses lookup tables to identify ratings for your auto insurance products. You can modify these lookup tables to reflect your ratings.

Did this article solve your issue?

Let us know so we can improve!

YesNo