---
title: "Essential Business Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_essential_business_rating_528429.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Essential Business Rating

Essential Business Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Essential Business Rating

When we quote and endorse the Commercial products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:

1.  Pull data from the Essential Business product model to form the rating input data.
    
2.  Call the rating procedure and rating input data to calculate the coverage prices.
    
3.  Take the coverage price data returned by the rating procedure, then inserts it into one or more pricing formulas in the product model.
    
4.  Roll up the coverage prices to the total (quoted) premium price.
    

For the Essential Business product, we use the **Rating\_EssentialBusiness** integration procedure that then calls the **EssentialBusiness** calculation procedure.

[](https://help.salesforce.com/s?language=en_US)

Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls the rating procedure to calculate the price for that quote.

Each insurer defines how they calculate prices for their insurance products. This rating procedure provides realistic examples for calculating small business insurance product prices. You can use our example as a guide as you decide how to create your own business insurance rating procedures.

[](https://help.salesforce.com/s?language=en_US)

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see Rating Procedures.

[](https://help.salesforce.com/s?language=en_US)

## Rating Procedure

For rating the Essential Business product, we use an integration procedure that you can find in OmniStudio Integration Procedures under:

-   Type/Subtype - Rating/EssentialBusiness
    
-   Integration Procedure Name - Rating\_EssentialBusiness
    

The integration procedure rates the business by calling the **EssentialBusiness** calculation procedure and passing these key-value pairs to it:

| 
Key

 | 

Value

 | 

What It Does

 |
| --- | --- | --- |
| 

includeInputKeys

 | 

BusLocation.instanceKey,productKey,parentProdKey

 | 

This option specifies the keys to include from the input set into the output sets of the calculation results. These keys are later used to identify the correct set of calculation results.

 |
| 

includeInputs

 | 

true

 | 

Turns on the code that pulls the instance keys specified by the includeInputKeys option.

 |

[](https://help.salesforce.com/s?language=en_US)

## Calculation Procedures

The Essential Business calculation procedure rates all the coverages for the quote. This calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.

We expect that you would like to create your own calculation procedure to rate your Commercial business owners products. You can use **EssentialBusiness** as an example or change it so you can see how calculation procedures work.

[](https://help.salesforce.com/s?language=en_US)Here's what each step of the **EssentialBusiness** calculation procedure does:

[](https://help.salesforce.com/s?language=en_US)

1.  Does matrix lookups to get the SIC Code and details of the business property.
    
2.  Does matrix lookups to get the business points for Business Age, Roof Age, Wiring Age, Hours, Plumbing, Location, Parking Lot, and the presence of Alarms and Parking Lots.
    
3.  Calculates the business points.
    
4.  Does matrix lookups to get more business details, SIC information, and deductibles.
    
5.  Calculates the base Premium.
    
6.  Does matrix lookups for coverages.
    
7.  Calculates the premium for employee fraud.
    
8.  Does matrix lookups to get information on the building sprinkler.
    
9.  Calculates the premium for the Accounts Receivable.
    
10.  Does matrix lookups to get information about any optional coverages that have been added.
     
11.  Calculates the premium for the Valuable Papers, Electronic Media, and Signage.
     
12.  Does matrix lookups for premiums for any rental or employee car.
     
13.  Calculates the Total Premium.
     

[](https://help.salesforce.com/s?language=en_US)EssentialBusiness includes aggregation steps that calculate aggregated premiums for specific coverages:

[](https://help.salesforce.com/s?language=en_US)

1.  Calculates the aggregate premium for personal property by taking the sum of final rate for personal property outputs from each run of the calculation steps.
    
2.  Calculates the aggregate premium for accounts receivables by taking the sum of final rate for accounts receivables outputs from each run of the calculation steps.
    
3.  Calculates the aggregate premium for general liability by taking the sum of final rate for general liability outputs from each run of the calculation steps.
    
4.  Calculates the aggregate premium for employee fraud by taking the sum of final rate for employee fraud outputs from each run of the calculation steps.
    
5.  Calculates the aggregate premium for rental car by taking the sum of final rate for rental car outputs from each run of the calculation steps.
    
6.  [](https://help.salesforce.com/s?language=en_US)
    
    Calculates the aggregate premium for employee auto by taking the sum of final rate for employee auto outputs from each run of the calculation steps.
    
7.  [](https://help.salesforce.com/s?language=en_US)
    
    Calculates the aggregate premium for valuable papers by taking the sum of final rate for valuable papers outputs from each run of the calculation steps.
    
8.  Calculates the aggregate premium for tenants liability by taking the sum of final rate for tenants liability outputs from each run of the calculation steps.
    
9.  Calculates the aggregate premium for total signage by taking the sum of final rate for total signage outputs from each run of the calculation steps.
    
10.  Calculates the aggregate premium for total base premium by taking the sum of final rate for total base premium outputs from each run of the calculation steps.
     

[](https://help.salesforce.com/s?language=en_US)

## Pricing Formulas

After the rating procedure runs for an in-progress quote, Vlocity goes back to the product model it's creating the quote for. On the product model, the total policy premium is calculated.

This rating happens on the Simulate tab of the product model. On the Essential Business product model **Simulate** tab, you see the Rating Inputs and Rating Outputs mapped from the rating procedure. To learn how to do this simulation, see [Map Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.")

The formula for total policy premium for the Essential Business product in the **Essential Business** > **Total Pricing Formula** field is:

totalSignage + totalTenantsLiability + totalEmployeeAuto + TotalRentalCar + TotalEmployeeFraud + TotalGl + TotalAR

[](https://help.salesforce.com/s?language=en_US)

## Next Steps

After you've gotten a look at the rating procedure, go to the Essential Business product models and try [simulating the rating procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") that's mapped to the product model.

Then you can go on to the [quote flows](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quote_business_process_1.htm&language=en_US&type=5 "We've created a quote business process for General Liability for you to examine, use as an example, and extend to create your own business processes for insurance.") to see how to generate a quote for Essential Business.

Did this article solve your issue?

Let us know so we can improve!

YesNo