---
title: "Commercial Auto Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_rating_527467.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Commercial Auto Rating

Commercial Auto Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Commercial Auto Rating

When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium. 

The service does the following to price the product:

1.  Pulls data from the Commercial Auto product model to form the rating input data.
    
2.  Calls the rating procedure and rating input data to calculate the coverage prices.
    
3.  Takes the coverage price data returned by the rating procedure, then inserts it into the product model.
    
4.  Rolls up the coverage prices to the vehicles using the vehicle pricing formula.
    
5.  Rolls up the vehicle prices to the total (quoted) premium price.
    

The rating procedure we use is the CommercialAutoRating Integration Procedure. It calculates the coverage prices for the Commercial Auto product. Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls this rating procedure to calculate the price for that quote.

[](https://help.salesforce.com/s?language=en_US)

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see Rating Procedures.

[](https://help.salesforce.com/s?language=en_US)

## Rating Input

To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Commercial Auto product includes a Vehicle insured item spec as the primary multi-instance item that auto policies will insure. You can create quotes for multiple vehicles.

The Driver insured party spec is a child of the Vehicle Insured Item spec, which lets a vehicle have multiple drivers.

All coverages in the model are children of the Vehicle insured item spec. This way, each vehicle quoted can have its own separately configured coverages.

[](https://help.salesforce.com/s?language=en_US)

## Rating Procedure

To rate the Commercial Auto insurance product, we use this Integration procedure:

-   Type/SubType - Rating/CommercialAuto
    
-   Integration Procedure Name - CommercialAutoRating
    

While you'll create your own integration procedure to rate your auto insurance products, you can look at and test out the structure of this one to see how it works. You can model your own Integration Procedure on this one if it works for you.

The Integration Procedure comprises of a calculation action that rates vehicles by calling the autoRateCommercialVehicles calculation procedure. This remote option is set:

-   [](https://help.salesforce.com/s?language=en_US)
    
    Key: includeInputs
    
    Value: true
    
    What it does: Turns on the code that pulls the instance keys specified by the includeInputKeys option.
    

We expect that you'll create your own calculation procedure to rate vehicles for your auto insurance products. You can use autoRateCommercialVehicles as a model, and make changes to it so you can see how calculation procedures work.

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
     

autoRateCommercialVehicles includes an aggregation step that calculate aggregated premiums per vehicle. This step calculates the sum of all the Commercial Auto premiums calculated from each run of the calculation steps.

These calculation matrices are used by autoRateCommercialVehicles calcuation proxedure:

| 
Calculation Matrix Name

 | 

Description

 |
| --- | --- |
| 

autoCarAltFuel

 | 

Handles customer input that says whether a car uses alternative fuels or not.

Takes a true or false input, and returns percentage outputs.

Cars with alternative fuels rate out at lower prices than cars without.

 |
| 

autoCarBrakes

 | 

Handles customer input that says whether a car has anti-lock brakes or not.

Takes a true or false input, and returns percentage outputs.

Cars with anti-lock brakes rate out at lower prices than cars without anti-lock brakes.

 |
| 

autoCarStability

 | 

Handles customer input that says whether a car has anti-lock brakes or not.

Takes a true or false input, and returns a percentage output.

Cars with stability control rate out slightly lower than cars without it.

 |
| 

autoCarSymbol

 | 

Takes a numeric input. Returns percentage outputs.

 |
| 

autoCarTheft

 | 

Handles customer input that says whether a car has an antitheft device or not.

Takes a true or false input. Returns a percentage output.

 |
| 

autoCarValue

 | 

Takes a numeric input. Returns numeric and percentage outputs.

 |
| 

autoCarYear

 | 

Handles customer input of the car's year.

Takes a numeric input. Returns percentage outputs.

 |
| 

autoDeductCCD

 | 

Handles the deductible a customer chooses.

Takes a numeric input. Returns a percentage output.

The higher the deductible chosen, the lower the rating.

 |
| 

autoLimitBIPD

 | 

Handles limits for bodily injury and property damage a customer chooses.

Takes numeric inputs. Returns a percentage output.

 |
| 

autoLimitMED

 | 

Handles the limit a customer chooses for medical expenses.

Takes a numeric value. Returns a percentage output.

The higher the limit chosen, the higher the rating.

 |
| 

autoLimitUM

 | 

Handles the limit for uninsured motorists a customer chooses.

Takes a split numeric value. Returns a percentage output.

 |
| 

deductCOLL

 | 

Handles the deductible a customer chooses for collision coverage.

Takes a numeric value. Returns a percentage output.

 |

[](https://help.salesforce.com/s?language=en_US)You can (and probably will) make changes to these calculation matrices to reflect the ratings for your auto insurance products.

[](https://help.salesforce.com/s?language=en_US)To learn the basics about Insurance rating procedures for pricing insurance products, see [Learn About Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures.htm&language=en_US&type=5 "Rating procedures are the backbone of insurance pricing. Learn how services, product models, and rating procedures work together to price insurance products.").

[](https://help.salesforce.com/s?language=en_US)

## Pricing Formulas

After the rating procedure returns the coverage prices, Vlocity uses the product model pricing formulas to roll up the prices. On the product model, the premium per vehicle is calculated, and the total policy premium is calculated.

[](https://help.salesforce.com/s?language=en_US)This happens on the Simulate tab of the product model. On the Commercial Auto product model's Simulate tab, you'll see the Rating Inputs and Rating Outputs mapped from the rating procedure. To learn how to do this, see [Map Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.")

[](https://help.salesforce.com/s?language=en_US)Under the Rating Output section of the Simulate tab, the formula to calculate the per-vehicle premium is in the **Commercial Auto** > **Total Pricing Formula** field. The total Pricing Formula is **TotalPremium**.

[](https://help.salesforce.com/s?language=en_US)

## Next Steps

After you've gotten a look at the rating procedure, go to the Commercial Auto product model and try [simulating the rating procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") that's mapped to the product model.

Then you can go on to the [quote flows](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_business_process_omnistudio.htm&language=en_US&type=5 "We've created a bunch of business processes for you to examine, use as examples, and extend to create your own business processes for auto insurance in Vlocity.") to see how the Auto Application rates products for quotes.

Did this article solve your issue?

Let us know so we can improve!

YesNo