---
title: "Learn About Rating Procedures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Learn About Rating Procedures

Learn About Rating Procedures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Learn About Rating Procedures

Rating procedures are the backbone of insurance pricing. Learn how services, product models, and rating procedures work together to price insurance products.

[](https://help.salesforce.com/s?language=en_US)

## What’s a Rating?

A rating is a risk-based calculation of a premium based on a set of input characteristics. For example, in an auto insurance policy, rating input characteristics include the type of vehicle, number of miles driven annually, and safety features on the car.

Ratings determine the cost a customer pays in exchange for the risk taken on by the insurance carrier.

Here's an example of a typical insurance rating formulation:

-   Base premium = (Amount of Coverage / $1000) \* Base Rate
    
-   Adjusted rate = Base Premium \* Rate Risk Factor
    
    Rate Risk Factor is a percentage adjustment to the base premium based on risk.
    
    | 
    Risk Level
    
     | 
    
    Rate Risk Factor
    
     | 
    
    Rate Adjustment
    
     |
    | --- | --- | --- |
    | 
    
    Low
    
     | 
    
    Less than 1
    
     | 
    
    Decrease in premium. With a factor of 0.9, the price is 90% of base premium.
    
     |
    | 
    
    Average
    
     | 
    
    1
    
     | 
    
    No adjustment. With a factor of 1, the price is 100% of base premium.
    
     |
    | 
    
    High
    
     | 
    
    Greater than 1
    
     | 
    
    Increase in premium. With a factor of 1.1, the price is 110% of base premium.
    
     |
    
-   Each coverage has its own coverage amount and formula.
    
-   Total Premium = Base Premium + All Coverage Premiums.
    

[](https://help.salesforce.com/s?language=en_US)

## Rating Procedures for Insurance Products

Rating procedures contain all the ratings information and calculations required for your users to rate insurance products according to customer needs.

An insurance product can use a single rating procedure, or have multiple rating procedures configured within its hierarchy. Many insurance products can use the same rating procedure. Rating procedures are mapped to your product specifications. Attributes are mapped for the inputs and outputs of the rating procedure.

When you quote, renew, and endorse an insurance product, the pricing services use the product model data, product rating procedure, and pricing formulas to price the coverages. The services:

1.  Pull data from the product model to form the rating input data.
    
2.  Call the rating procedure and rating input data to calculate the coverage prices.
    
3.  Take the coverage price data returned by the rating procedure, then inserts it into the product model.
    
4.  Roll up the coverage prices to the total (quoted) premium price.
    

Some services that rate products are `InsProductService:getRatedProducts`, `InsProductService:rePriceProduct`, `InsQuoteService:priceRootItem`, and `InsQuoteService:updateQuoteLine`.

[](https://help.salesforce.com/s?language=en_US)

## How Rating Procedures and Product Specs Fit Together

Create rating procedures with all input and outputs before you create root product specs and child product specs. Then, when it's time to map rating procedures to products, everything is ready to go. You can reuse input mappings on coverage specs (which are children of root product specs) if you're using the same coverage specs in multiple root products.

Learn more in [Mapping Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.").

Did this article solve your issue?

Let us know so we can improve!

YesNo