---
title: "Commercial Auto Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_commercial_auto_overview_526808.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Commercial Auto Overview

Commercial Auto Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Commercial Auto Overview

The Commercial line of business gives you a fully functional example of the Commercial Auto product models, rating procedures, and business processes for quoting and issuing policies.

You can use the models and processes as a reference to develop your own product models and business processes or extend them and make them your own.

[](https://help.salesforce.com/s?language=en_US)

## Product Models and Rating Procedures

The product model and the rating procedure that calculate prices for Commercial Auto at runtime underpin all the business processes.

-   Product Model: Commercial Auto
    
-   Rating Procedure: CommercialAutoRating
    

The product model provides the structure for the data JSON that moves through the business processes. The Commercial Auto product model is single-instance, which means that we intend customers to insure only one business per policy. All coverages have been designed to be configured at the policy level.

To learn more about the product model, see [Commercial Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_product_model_526841.htm&language=en_US&type=5 "The Commercial Auto product is a single-instance product model that lets businesses create quotes for multiple vehicles that are tied to a single location.").

The rating procedures take information from the prospective customer (that becomes attribute values in the data JSON) during quoting business processes. The procedures calculate the prices for coverages, then the product model rating simulation rolls up those prices and calculates the total premium.

To learn more about these rating procedures, see [Commercial Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_rating_527467.htm&language=en_US&type=5 "When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium.").

[](https://help.salesforce.com/s?language=en_US)

## Business Processes

This process guides prospective customers (and agents and brokers helping those prospects) to get a rated quote for a business product:

-   [Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quote_business_process_1.htm&language=en_US&type=5 "We've created a quote business process for General Liability for you to examine, use as an example, and extend to create your own business processes for insurance.")
    

[](https://help.salesforce.com/s?language=en_US)Note

To use these features for business owners insurance, [request a reference org](https://help.salesforce.com/s/articleView?id=ind.insurance_get_started_app_suite_orgs.htm&language=en_US&type=5#insurance_get_started_app_suite_orgs "Insurance business apps are pre-built solutions created with industry experts to help you modernize your business and focus more on your customers. These apps are delivered through reference orgs that include the Insurance managed package. To accelerate your digital transformation, these reference orgs also have sample configuration and seed data you can migrate into your production org. Industries Business App reference orgs are only available to current customers and partners.") for Property and Casualty.

[](https://help.salesforce.com/s?language=en_US)

## What's Next

Now that you've got a high-level intro to the Commercial line of business, look at the [Commercial Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_product_model_526841.htm&language=en_US&type=5 "The Commercial Auto product is a single-instance product model that lets businesses create quotes for multiple vehicles that are tied to a single location.").

-   **[Commercial Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_product_model_526841.htm&language=en_US&type=5)**  
    The Commercial Auto product is a single-instance product model that lets businesses create quotes for multiple vehicles that are tied to a single location.
-   **[Commercial Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_auto_rating_527467.htm&language=en_US&type=5)**  
    When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium. 
-   **[Create a Commercial Auto Quote Using OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_commercial_auto_quote_using_omniscript_omnistudio.htm&language=en_US&type=5)**  
    Add details to create a quote for a Commercial Auto Policy with multiple vehicles associated with multiple locations.

Did this article solve your issue?

Let us know so we can improve!

YesNo