---
title: "Multi Auto Rating"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multi Auto Rating

Multi Auto Rating[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multi Auto Rating

The rating procedure we use is the auto\_MultiInstanceRating Integration Procedure. It calculates the coverage prices for the Multi Auto product. Any time a broker or customer service rep generates a quote for a potential customer, the quote business process calls this rating procedure to calculate the price for that quote.

Here's what that looks like for the Multi Auto product:

To learn the basics about Vlocity Insurance rating procedures for pricing insurance products, see [](https://help.salesforce.com/s?language=en_US)[Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures_super.htm&language=en_US&type=5 "Rating procedures make it possible to price insurance products. Set up, map, and implement rating procedures for all your products and plans.").

## Rating Input

To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Multi Auto product includes a Vehicle insured item spec as the primary multi-instance item that auto policies will insure. You can create quotes for multiple vehicles.

For a deep dive into the rating input for the Multi Auto product, see [Multi Auto Rating Input](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_input_omnistudio.htm&language=en_US&type=5 "To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Multi Auto product includes a Vehicle insured item spec as the primary multi-instance item that auto policies will insure. You can create quotes for multiple vehicles.").

## Rating Procedure

A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.

For details of the Multi Auto rating procedure, see [Multi Auto Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_procedure_omnistudio.htm&language=en_US&type=5 "A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.").

## Pricing Formulas

After the rating procedure returns the coverage prices, Vlocity uses the product model pricing formulas to roll up the prices. On the product model, the premium per vehicle is calculated, and the total policy premium is calculated.

Here's what that looks like:

This happens on the Simulate tab of the product model. On the Multi Auto product model's Simulate tab, you'll see the Rating Inputs and Rating Outputs mapped from the rating procedure. To learn how to do this, see [](https://help.salesforce.com/s?language=en_US)[Mapping Ratings to Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.").

Under the Rating Output section of the Simulate tab, the formula to calculate the per-vehicle premium is in the **Vehicle** > **Total Pricing Formula** field. The Vehicle Total Pricing Formula is:

premiumBIPD + premiumCOLL + premiumCCD + premiumMED + premiumUM+premiumRental

The formula total policy premium for this product is in the **Multi Auto** > **Total Pricing Formula** field. The Multi Auto Total Pricing Formula is:

SUM(premiumBIPD + premiumCOLL + premiumCCD + premiumMED + premiumUM+premiumRental)

## Next Steps

After you've gotten a look at the rating procedure, go to the Multi Auto product model and try [simulating the rating procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") that's mapped to the product model.

Then you can go on to the [quote flows](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_business_process_omnistudio_2.htm&language=en_US&type=5 "We've created a bunch of business processes for you to examine, use as examples, and extend to create your own business processes for auto insurance in Vlocity.") to see how the Auto Application rates products for quotes.

-   **[Multi Auto Rating Input](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_input_omnistudio.htm&language=en_US&type=5)**  
    To understand the construction of the rating procedure, you need to understand the form of the input data passed into the procedure. The Multi Auto product includes a Vehicle insured item spec as the primary multi-instance item that auto policies will insure. You can create quotes for multiple vehicles.
-   **[Multi Auto Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_rating_procedure_omnistudio.htm&language=en_US&type=5)**  
    A rating is a risk-based calculation of a premium based on a set of input characteristics. We use rating procedures to price insurance products and health plans. You'll set up, map, and implement rating procedures for all your products and plans.

Did this article solve your issue?

Let us know so we can improve!

YesNo