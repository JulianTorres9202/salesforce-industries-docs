---
title: "Business Owners Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_rating_520335.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Business Owners Rating

Business Owners Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Business Owners Rating

When we quote and endorse the Business Owners Policy products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:

-   Pull data from the Business Owners product model to form the rating input data.
    
-   Call the rating procedure and rating input data to calculate the coverage prices.
    
-   Take the coverage price data returned by the rating procedure, then inserts it into the pricing formula(s) in the product model.
    
-   Roll up the coverage prices to the total (quoted) premium price.
    

Here's what that looks like for the Superior and Economy business products:

The rating procedure we use to rate the Superior Business and Economy Business products is the **BusinessOwnersPolicy** calculation procedure.

For the Essential Business product, we use the **Rating\_EssentialBusiness** integration procedure that then calls the **EssentialBusiness** calculation procedure. For details on this rating procedure, see [Essential Business Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_essential_business_rating_528429.htm&language=en_US&type=5 "When we quote and endorse the Commercial products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:").

[](https://help.salesforce.com/s?language=en_US)

Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls the rating procedure to calculate the price for that quote.

Each insurer defines how they will calculate prices for their insurance products. This rating procedures provide realistic examples for calculating small business insurance product prices. You can use our example as a guide as you decide how to create your own business insurance rating procedures.

[](https://help.salesforce.com/s?language=en_US)

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see Rating Procedures.

[](https://help.salesforce.com/s?language=en_US)

## Rating Input

To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Superior Business and Economy Business products include a smallBusiness insured item spec as the insured item. 

You can add or remove optional coverages and modify their respective deductibles. All coverages in these models are associated directly to the root product specs.

To learn more about these product models, see [Business Owners Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_product_model_519730.htm&language=en_US&type=5 "To understand how the Business Owners' application works, you need to figure out how it's built. Read on to understand the Business Owners' product model.").

[](https://help.salesforce.com/s?language=en_US)

## Rating Procedure

Here's a top-level view of how the Business Owners rating procedure rates both the Economy Business and Superior Business products. This formula is mapped from the output of the calculation procedure.

[](https://help.salesforce.com/s?language=en_US)

## Calculation Procedures

The Business Owners calculation procedure rates all the coverages for the quote for both the Economy Business and Superior Business products.

This calculation procedure includes variables, constants, and calculation steps. Some of those calculation steps are matrix lookups that call specific calculation matrices.

We expect that you'll create your own calculation procedure to rate your business owners products. You can use **BusinessOwnersPolicy** as an example, and make changes to this procedure so you can see how calculation procedures work.

To learn more about creating and editing calculation procedures in general, see .Calculation Procedures and Matrices

The meat of the calculation procedure is its calculation steps. Here's what each step of the **BusinessOwnersPolicy** calculation procedure does:

-   Does matrix lookups to get the SIC Code and details of the business property.
    
-   Calculates the business points.
    
-   Does matrix lookups to get more business details, SIC information, and deductibles.
    
-   Calculates the base Premium.
    
-   Does matrix lookups for coverages.
    
-   Calculates the premium for employee fraud.
    
-   Does matrix lookups to get information on the building sprinkler.
    
-   Calculates the premium for the Accounts Receivable.
    
-   Does matrix lookups to get information about any optional coverages that have been added.
    
-   Calculates the total premium for the Small Business.
    

[](https://help.salesforce.com/s?language=en_US)BusinessOwnersPolicy includes aggregation steps that calculate aggregated premiums for specific coverages:

[](https://help.salesforce.com/s?language=en_US)

-   Calculates the aggregate premium for personal property by taking the sum of final rate for personal property outputs from each run of the calculation steps.
    
-   Calculates the aggregate premium for accounts receivables by taking the sum of final rate for accounts receivables outputs from each run of the calculation steps.
    
-   Calculates the aggregate premium for general liability by taking the sum of final rate for general liability outputs from each run of the calculation steps.
    
-   Calculates the aggregate premium for employee fraud by taking the sum of final rate for employee fraud outputs from each run of the calculation steps.
    
-   Calculates the aggregate premium for rental car by taking the sum of final rate for rental car outputs from each run of the calculation steps.
    

[](https://help.salesforce.com/s?language=en_US)

## Pricing Formulas

After the rating procedure runs for an in-progress quote, Vlocity goes back to the product model it's creating the quote for. On the product model, the total policy premium is calculated.

This happens on the Simulate tab of the product model. On the Superior Business, Economy Business, and Essential Business product model **Simulate** tabs, you'll see the Rating Inputs and Rating Outputs mapped from the rating procedure. To learn how to do this, see [Map Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.")

The formula total policy premium for the Economy Business product in the **Economy Business** > **Total Pricing Formula** field is:

basePremium + premGenLiab\_\_premGenlLiab + premTenantLiability\_\_premTenantLiab + premSignage + premAR + premValuePapers + premEmpFraud + premRentalCar\_\_premRentalCar + premElectronicMedia + premEmployeeAuto\_\_premEmployeeAuto + rateBusProperty\_\_ratePersonalProperty

The formula total policy premium for the Superior Business product in the **Superior Business** > **Total Pricing Formula** field is:

basePremium + premGenLiab\_\_premGenlLiab + premTenantLiability\_\_premTenantLiab + rateBusProperty\_\_ratePersonalProperty + premSignage + premAR + premValuePapers + premEmpFraud + premRentalCar\_\_premRentalCar + premElectronicMedia + premEmployeeAuto\_\_premEmployeeAuto

[](https://help.salesforce.com/s?language=en_US)

## Next Steps

After you've gotten a look at the rating procedure, go to the Superior Business and Economy Business product models and try [simulating the rating procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") that's mapped to the product model.

Then you can go on to the [quote flowsProperty Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_property_quote_business_process_517662.htm&language=en_US&type=5 "We've created a quote business process for Homeowners and Renters insurance for you to examine, use as examples, and extend to create your own business processes for property insurance in Vlocity.") to see how the Business Owners Application rates products for quotes.

Did this article solve your issue?

Let us know so we can improve!

YesNo