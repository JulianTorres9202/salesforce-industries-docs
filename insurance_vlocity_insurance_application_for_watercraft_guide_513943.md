---
title: "Insurance Application for Watercraft Guide"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_application_for_watercraft_guide_513943.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Application for Watercraft Guide

Insurance Application for Watercraft Guide[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Application for Watercraft Guide

The Insurance Application for Property & Casualty includes a fully functioning policy administration and claims system for marine insurance.

[](https://help.salesforce.com/s?language=en_US)

This Application can be used for reference or as the base for the development of product models and business processes.

This guide will orient you to the contents of the org and the business process for marine insurance.

[](https://help.salesforce.com/s?language=en_US)

## Product Modeling, Rating, and Business Processes

The first major task a user does in Vlocity Insurance is product modeling. The product models you create define all the products you sell and service, and how Vlocity handles those products.

The next task is creating rating procedures to price the products you've modeled, then connecting those rating procedures to your products.

In the Vlocity Insurance Application for Property & Casualty, we've created several product models and rating procedures to price them. In this document, we'll be using the marine product model.

Now comes the fun part: Using the product models and rating procedures to create business processes to quote, sell, and service your insurance products.

Here are business processes available in the Vlocity Insurance Application for Property & Casualty that appear in this guide:

-   Quote
    
    Users can configure, price (rate), underwrite, and present quotes to end customers.
    
-   Issue Policy
    
    Users can choose payment schedules and methods, enter payment information, and issue an insurance policy.
    
-   Modify Policy (Add Endorsements/MTAs)
    
    Users can add endorsements to in-force policies.
    
-   Cancel Policy
    
    Users can cancel in-force policies and issue refunds to end customers as needed.
    

In addition to the business processes described in this guide, the Insurance business app for Property & Casualty includes business processes for renewing a policy.

[](https://help.salesforce.com/s?language=en_US)Note

To use these features for this marine insurance, [request a reference org](https://help.salesforce.com/s/articleView?id=ind.insurance_get_started_app_suite_orgs.htm&language=en_US&type=5#insurance_get_started_app_suite_orgs "Insurance business apps are pre-built solutions created with industry experts to help you modernize your business and focus more on your customers. These apps are delivered through reference orgs that include the Insurance managed package. To accelerate your digital transformation, these reference orgs also have sample configuration and seed data you can migrate into your production org. Industries Business App reference orgs are only available to current customers and partners.") with the Property & Casualty orgbusiness app.

-   **[Watercraft Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_watercraft_product_model_513979.htm&language=en_US&type=5)**  
    The product model underpins all the business processes used in the Watercraft line of business. The name of this product model is **Marine**.
-   **[Watercraft Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_watercraft_attribute_catalog_514260.htm&language=en_US&type=5)**  
    In this catalog, all attributes used for the Watercraft line of business are listed by Attribute Category. Each Attribute Category has its own table, which includes attribute codes and the product specs the attributes are used by.
-   **[Watercraft Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_watercraft_rating_514632.htm&language=en_US&type=5)**  
    When we quote and endorse the Marine product, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vessels, and total premium.  The service does the following to price the product:
-   **[Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_business_process_514979.htm&language=en_US&type=5)**  
    We've created a bunch of business processes for you to examine, use as examples, and extend to create your own business processes for auto insurance in Vlocity.
-   **[Endorsements/MTAs for Watercraft Business Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_endorsements_mtas_for_watercraft_business_processes_515631.htm&language=en_US&type=5)**  
    We've created a bunch of policy endorsement/MTA business processes for you to examine, use as examples, and extend to create your own endorsement/MTA business processes for watercraft insurance in Vlocity.

Did this article solve your issue?

Let us know so we can improve!

YesNo