---
title: "Product Models and Rating Procedures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_product_models_and_rating_procedures_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Product Models and Rating Procedures

Product Models and Rating Procedures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Models and Rating Procedures

The product model and the rating procedure that calculate prices for Commercial Auto at runtime underpin all the business processes.

-   Product Model: Commercial Auto
    
-   Rating Procedure: CommercialAutoRating
    

The product model provides the structure for the data JSON that moves through the business processes. The Commercial Auto product model is single-instance, which means that we intend customers to insure only one business per policy. All coverages have been designed to be configured at the policy level.

To learn more about the product model, see [Commercial Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_product_model_omnistudio.htm&language=en_US&type=5 "The Commercial Auto product is a single-instance product model that lets businesses create quotes for multiple vehicles that are tied to a single location.").

The rating procedures take information from the prospective customer (that becomes attribute values in the data JSON) during quoting business processes. The procedures calculate the prices for coverages, then the product model rating simulation rolls up those prices and calculates the total premium.

To learn more about these rating procedures, see [Commercial Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_rating_omnistudio.htm&language=en_US&type=5 "When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium.").

Did this article solve your issue?

Let us know so we can improve!

YesNo