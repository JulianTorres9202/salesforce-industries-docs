---
title: "Workers Compensation Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_overview_528667.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Workers Compensation Overview

Workers Compensation Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Workers Compensation Overview

The Commercial line of business gives you a fully functional example of the Workers Compensation product models, rating procedures, and business processes for quoting.

[](https://help.salesforce.com/s?language=en_US)

You can use this application for reference or as a base to develop your own product models and business processes.

[](https://help.salesforce.com/s?language=en_US)

## Product Models and Rating Procedures

The product model and the rating procedure that calculate prices for Workers Compensation products at runtime underpin all the business processes in this line of business:

-   Product Model: Workers Compensation
    
-   Rating Procedure: WorkersCompensationNCCIRating
    

The product model provides the structure for the data JSON that moves through the business processes. The Workers Compensation product model is single-instance, which means that we intend customers to insure only one Business Insured Item per quote. All coverages have been designed to be configured at the policy level.

To learn more about these product models, see [Workers Compensation Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_product_model_528700.htm&language=en_US&type=5 "To understand how the Workers Compensation application works, you need to figure out how the General Liability product is built.").

The rating procedures take information from the prospective customer (that becomes attribute values in the data JSON) during quoting business processes. The procedures calculate the prices for coverages, then the product model rating simulation rolls up those prices and calculates the total premium.

To learn more about these rating procedures, see [Workers Compensation Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_rating_529012.htm&language=en_US&type=5 "When we quote and endorse the Workers Compensation product, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:").

[](https://help.salesforce.com/s?language=en_US)

## Business Processes

This process guides prospective customers (and agents and brokers helping those prospects) to get a rated quote for a commercial product:

-   [Commercial Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_commercial_quote_business_process_1.htm&language=en_US&type=5 "We've created a quote business process for General Liability for you to examine, use as an example, and extend to create your own business processes for insurance.")
    

[](https://help.salesforce.com/s?language=en_US)

## What's Next

Now that you've got a high-level intro to the General Liability line of business, look at the [Workers Compensation Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_product_model_528700.htm&language=en_US&type=5 "To understand how the Workers Compensation application works, you need to figure out how the General Liability product is built.").

-   **[Workers Compensation Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_product_model_528700.htm&language=en_US&type=5)**  
    To understand how the Workers Compensation application works, you need to figure out how the General Liability product is built.
-   **[Workers Compensation Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_attribute_catalog_528822.htm&language=en_US&type=5)**  
    We've listed all the attributes used in the Workers Compensation application here by the category they fall under.
-   **[Workers Compensation Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_workers_compensation_rating_529012.htm&language=en_US&type=5)**  
    When we quote and endorse the Workers Compensation product, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:

Did this article solve your issue?

Let us know so we can improve!

YesNo