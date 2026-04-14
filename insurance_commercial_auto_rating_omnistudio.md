---
title: "Commercial Auto Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_rating_omnistudio.htm&language=en_US&type=5"
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
    
2.  Calls the rating procedure and rating input data to calculate the coverage prices. The rating procedure is mapped to the vehicle (Insured Item Spec) for the Multi Auto product.
    
3.  Takes the coverage price data returned by the rating procedure, then inserts it into the product model.
    
4.  Rolls up the coverage prices to the vehicles using the vehicle pricing formula.
    
5.  Rolls up the vehicle prices to the total (quoted) premium price.
    

The rating procedure we use is the CommercialAutoRating Integration Procedure. It calculates the coverage prices for the Commercial Auto product. Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls this rating procedure to calculate the price for that quote.

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see [](https://help.salesforce.com/s?language=en_US)[Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures.htm&language=en_US&type=5 "Rating procedures are the backbone of insurance pricing. Learn how services, product models, and rating procedures work together to price insurance products.").

After you've looked at the rating procedure, go to the Commercial Auto product model and try [simulating the rating procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") that's mapped to the product model. Then you can go on to the [quote flows](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_business_process_omnistudio_2.htm&language=en_US&type=5 "We've created a bunch of business processes for you to examine, use as examples, and extend to create your own business processes for auto insurance in Vlocity.") to see how the Auto Application rates products for quotes.

SEE ALSO

-   [Business Rule Engine](https://help.salesforce.com/s/articleView?id=ind.business_rules_engine.htm&language=en_US&type=5)
    

-   **[Rating Input for Commercial Auto](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_input_for_commercial_auto_omnistudio.htm&language=en_US&type=5)**  
    To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Commercial Auto product includes a Vehicle insured item spec as the primary multi-instance item that auto policies will insure. You can create quotes for multiple vehicles.
-   **[Rating Procedure for Commercial Auto](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedure_for_commercial_auto_reference_omnistudio.htm&language=en_US&type=5)**  
    To rate the Commercial Auto insurance product, we use this Integration procedure:
-   **[autoRateCommercialVehicles Lookup Tables](https://help.salesforce.com/s/articleView?id=ind.insurance_autoratecommercialvehicles_lookup_tables_omnistudio.htm&language=en_US&type=5)**  
    The autoRateCommercialVehicles expression set uses lookup tables to identify ratings for your auto insurance products. You can modify these lookup tables to reflect your ratings.
-   **[Pricing Formulas](https://help.salesforce.com/s/articleView?id=ind.insurance_pricing_formulas_uuid-59e72616-cedd-4044-80f9-46c7e160dfd6_section-idm4593021939556832727385503568.htm&language=en_US&type=5)**  
    After the rating procedure returns the coverage prices, Vlocity uses the product model pricing formulas to roll up the prices. On the product model, the premium per vehicle is calculated, and the total policy premium is calculated.

Did this article solve your issue?

Let us know so we can improve!

YesNo