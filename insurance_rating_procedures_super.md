---
title: "Build Rating Procedures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures_super.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Build Rating Procedures

Build Rating Procedures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Build Rating Procedures

Rating procedures make it possible to price insurance products. Set up, map, and implement rating procedures for all your products and plans.

-   **[Learn About Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures.htm&language=en_US&type=5)**  
    Rating procedures are the backbone of insurance pricing. Learn how services, product models, and rating procedures work together to price insurance products.
-   **[Rating Procedure Best Practices](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_best_practices_610890.htm&language=en_US&type=5)**  
    Setting up your first rating procedure? These best practices help you optimize your rating implementations.
-   **[Create Rating Procedures for Insurance Products](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_rating_procedures_610011.htm&language=en_US&type=5)**  
    Before you start plugging rating information into rating procedures, analyze your existing rating system and the steps involved in pricing insurance products. Then translate these steps into lookup tables, expression sets, and Integration Procedures.
-   **[Create Sharing Rules for Rating Procedure Components](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_sharing_rules.htm&language=en_US&type=5)**  
    If you use calculation procedures or expression sets in product ratings, ensure that quoting works for partner users who issue quotes using the Broker Portal. Create sharing rules that give partner users read-only access to the objects used by rating procedures.
-   **[Map Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5)**  
    After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.
-   **[Integration Procedure as Rating Procedure](https://help.salesforce.com/s/articleView?id=ind.insurance_integration_procedure_as_rating_procedure_610568.htm&language=en_US&type=5)**  
    If you calculate ratings for multi-instance insurance products or health plans, or if you use a third-party rating engine, use an Integration Procedure as a rating procedure.
-   **[External Rating and Pricing](https://help.salesforce.com/s/articleView?id=ind.insurance_external_rating_and_pricing_610958.htm&language=en_US&type=5)**  
    For external rating and `createUpdateQuote`, you must use the simplified quote JSON optimized for ease of mapping with external policy admin systems. You can generate a simplified quote JSON response using the `[InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")` service.

Did this article solve your issue?

Let us know so we can improve!

YesNo