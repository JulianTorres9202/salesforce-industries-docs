---
title: "Property Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_property_rating_517293.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Property Rating

Property Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Property Rating

When we quote and endorse the Homeowners and Renters products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The service does the following:

1.  Pulls data from the Homeowners or Renters product model to form the rating input data.
    
2.  Calls the rating procedure and rating input data to calculate the coverage prices.
    
3.  Takes the coverage price data returned by the rating procedure, then inserts it into the product model.
    
4.  Rolls up the coverage prices to the total (quoted) premium price.
    

The rating procedure we use to rate the Homeowners product is the **propHO3RatingProcedure\_ho3** expression set. The rating procedure that rates the Renters product is the **propHO4RatingProcedure\_ho4** expression set.

Note Before activating your expression set, run simulations with default and custom test input variables. Different decision matrices or sub expression versions called in an expression set version can have different start date time and end date time values. Test different versions by changing the Effective Date value. If the expression set doesn't work as expected, edit the elements and resimulate. When you're satisfied, activate the expression set. For more information, see ​[Simulate and Activate Your Expression Set Version​​](https://help.salesforce.com/s/articleView?id=ind.simulate_and_activate_the_expression_set.htm&language=en_US&type=5).

Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls the appropriate rating procedure to calculate the price for that quote.

Each insurer defines how they will calculate prices for their insurance products. These rating procedures provide realistic examples for calculating property insurance product prices. You can use our example as a guide as you decide how to create your own property insurance rating procedures.

[](https://help.salesforce.com/s?language=en_US)

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see Rating Procedures.

[](https://help.salesforce.com/s?language=en_US)

## Rating Input

To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Homeowners and Renters products include a Home insured item spec as the insured item. Both product models include a Scheduled Item insured item spec as a child of the Home insured item spec.

All coverages in these models are associated directly to the root product specs.

To learn more about these product models, see [Property Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_property_product_model_516441.htm&language=en_US&type=5 "The product models underpin all the business processes used in the Property line of business. The name of these product models are:").

[](https://help.salesforce.com/s?language=en_US)

## Rating Procedure

Rating procedures are used to price insurance products and health plans. The property line of business provides these rating procedures for the two root products:

-   [Homeowners Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_homeowners_calculation_procedure_517363.htm&language=en_US&type=5 "This calculation procedure rates all the coverages for a quote generate using the Homeowners root product.")
    
    To rate the homeowners product, use this integration procedure:
    
    -   Type: insRating ​ ​ ​
        
    -   Subtype: propertyOwner ​ ​ ​
        
    -   Name: PropertyRating
        

Here's how the Homeowners rating procedure rates the Homeowners product at the top level.

-   [Renters Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_renters_calculation_procedure_517541.htm&language=en_US&type=5 "This calculation procedure rates all the coverages for a quote generate using the Renters root product.")
    
    To rate the renters product, use this integration procedure:
    
    -   Type: insRating ​ ​ ​
        
    -   Subtype: property
        
    -   Renter ​ ​ ​ Name: PropertyRentersRating
        

Here's how the Renters rating procedure rates the Renters product at the top level.

Note From Summer '22 onwards, the homeowners (HO3) and renters products (HO4) will use Business Rule Engine components for rating premiums. The existing customers can still use calculation procedures and decision matrices as rating engine by using:

-   insRating/propertyOwner integration procedure for the homeowners (HO3) product ​ ​ ​
    
-   insRating/propertyRenter integration procedure for the renters (HO4) product
    

[](https://help.salesforce.com/s?language=en_US)

## Pricing Formulas

After the rating procedure runs for an in-progress quote, Vlocity goes back to the product model it's creating the quote for. On the product model, the total policy premium is calculated.

This happens on the Simulate tab of the product model. On the Homeowners and Renters product model Simulate tabs, you'll see the Rating Inputs and Rating Outputs mapped from the rating procedure. To learn how to do this, see [Map Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.")

The formula total policy premium for the Homeowners product in the **Homeowners (HO3)** > **Total Pricing Formula** field is:

​​SUM (premiumJWY + premiumMUSICEQP + premiumCAMERA + premiumBIKE + premiumFA + premiumBldOrdinance + premiumLossOfUse + premiumMedPay + premiumLiability + premiumSewer + premiumContent + premiumOtherStructures + premiumDwelling)​​

The formula total policy premium for the Renters product in the **Renters (HO4)** > **Total Pricing Formula** field is:

SUM (premiumCTS + premiumSVAL + premiumLossOfUse + premiumMedPay + premiumLiability + premiumBIKE + premiumCAMERA + premiumFA + premiumJWY + premiumMUSICEQP)​

[](https://help.salesforce.com/s?language=en_US)

## Next Steps

After you've gotten a look at the rating procedure, go to the Homeowners and Renters product models and try [simulating the rating procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") that's mapped to the product model.

Then you can go on to the [quote flows](https://help.salesforce.com/s/articleView?id=ind.insurance_property_quote_business_process_517662.htm&language=en_US&type=5 "We've created a quote business process for Homeowners and Renters insurance for you to examine, use as examples, and extend to create your own business processes for property insurance in Vlocity.") to see how the Property Application rates products for quotes.

-   **[Homeowners Calculation Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_homeowners_calculation_procedure_517363.htm&language=en_US&type=5)**  
    This calculation procedure rates all the coverages for a quote generate using the Homeowners root product.
-   **[Renters Calculation Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_renters_calculation_procedure_517541.htm&language=en_US&type=5)**  
    This calculation procedure rates all the coverages for a quote generate using the Renters root product.

Did this article solve your issue?

Let us know so we can improve!

YesNo