---
title: "Workers Compensation Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_rating_529012.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Workers Compensation Rating

Workers Compensation Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Workers Compensation Rating

When we quote and endorse the Workers Compensation product, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:

1.  Pull data from the Workers Compensation product model to form the rating input data.
    
2.  Call the rating procedure and rating input data to calculate the coverage prices.
    
3.  Take the coverage price data returned by the rating procedure, then inserts it into the pricing formula(s) in the product model.
    
4.  Roll up the coverage prices to the total (quoted) premium price.
    

The rating procedure we use to rate the Workers Compensation is the **insRating\_WorkersCompensationNCCI** integration procedure. Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls the rating procedure to calculate the price for that quote.

[](https://help.salesforce.com/s?language=en_US)

Each insurer defines how they will calculate prices for their insurance products. This rating procedures provide realistic examples for calculating commercial insurance product prices. You can use our example as a guide as you decide how to create your own business insurance rating procedures.

[](https://help.salesforce.com/s?language=en_US)

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see Rating Procedures.

[](https://help.salesforce.com/s?language=en_US)

## Rating Input

To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Workers Compensation product includes the Building and Location insured item specs. The Payroll Classification insured party spec is a child item of the Location insured item spec.

You can modify their respective deductibles. All coverages in these models are associated directly to the root product specs.

To learn more about these product models, see [Workers Compensation Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_product_model_528700.htm&language=en_US&type=5 "To understand how the Workers Compensation application works, you need to figure out how the General Liability product is built.").

[](https://help.salesforce.com/s?language=en_US)

## Rating Procedure

For Workers Compensation, we use the integration procedure:

-   Type/Subtype - insRating/WorkersCompensationNCCi
    
-   Version - WorkersCompensationNCCIRating
    

The integration procedure rates the business by calling two calculation procedures - **WorkersCompensationNCCI** and **WorkersCompensationLiabilityAndSchedule**.

For more information on the **WorkersCompensationNCCIRating** rating procedure, see [Workers Compensation Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_rating_procedure_529064.htm&language=en_US&type=5 "A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.").

[](https://help.salesforce.com/s?language=en_US)

## Pricing Formulas

The total policy premium is calculated on the product model. This happens on the Simulate tab of the product model. On the Simulate tab, you see the Rating Inputs and Rating Outputs mapped from the rating procedure. To learn how to do this, see [Map Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.")

The formula total policy premium for the Workers Compensation product in the **General Liability** > **Total Pricing Formula** field is SUM(CoverageAPremium) + EmplLiabilityPremium - scheduleDiscountCalculatedAmt + experienceRatingModCalculatedAmt + longshoreHarborWorkersCompFinalPremium + waiverOfSubroFinalPremium.

[](https://help.salesforce.com/s?language=en_US)

## Next Steps

After you've gotten a look at the rating procedure, go to the Workers Compensation product model in your org and try [simulating the rating procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") that's mapped to the product model.

Then you can go on to the [quote flows](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quote_business_process_1.htm&language=en_US&type=5 "We've created a quote business process for General Liability for you to examine, use as an example, and extend to create your own business processes for insurance.") to see how the Workers Compensation rates products for quotes.

-   **[Workers Compensation Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_rating_procedure_529064.htm&language=en_US&type=5)**  
    A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.

Did this article solve your issue?

Let us know so we can improve!

YesNo