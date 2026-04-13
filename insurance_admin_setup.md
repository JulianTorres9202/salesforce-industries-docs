---
title: "Set Up Digital Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_setup.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up Digital Insurance

Set Up Digital Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Digital Insurance

Define the insurance products that you sell to customers, including their classifications, categories, and attributes. Create customized price adjustment methods and pricing procedures. Define rules that determine how your products behave when they're quoted, sold, and serviced.

Note Insurance Cloud works with Revenue Cloud and Context Service to manage products, context, pricing, configuration, rules, surcharges, and quoting.

A Digital Insurance implementation relies on Revenue Cloud and Context Service. Review these sections as you work through your implementation.

-   **[Enable Revenue Settings for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_enable_revenue.htm&language=en_US&type=5)**  
    Digital Insurance works with Revenue Cloud to manage products and other tasks. Before you can use Insurance products, pricing, and rules to create quotes and manage policies, you must enable some Revenue Cloud settings.
-   **[Set Up Digital Insurance Products](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_products.htm&language=en_US&type=5)**  
    Create a product catalog to organize and sell all the insurance products and services that your company offers to customers. Setting up insurance products defines what your company sells and how it’s structured, to help you deliver accurate quotes and a seamless customer experience.
-   **[Set Up Digital Insurance Context and Pricing](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_context_pricing.htm&language=en_US&type=5)**  
    Insurance pricing, also called rating, turns product selections, risk attributes, and customer data into traceable premiums.
-   **[Set Up Product Configurator](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_product_configurator.htm&language=en_US&type=5)**  
    Grant users access to the Product Configurator features.
-   **[Product Underwriting Rules for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_product_underwriting_rules.htm&language=en_US&type=5)**  
    Define the criteria for transitioning a quote record to the target stage. Product underwriting rules set the conditions for the root product that determine the quote's progress. After you define stage definitions and configure stage transitions, create underwriting rules to define the transition criteria for those stages.
-   **[Product Configuration Rules for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_product_configuration_rules.htm&language=en_US&type=5)**  
    Simplify configuration experience and reduce configuration errors with configuration rules. When you configure products in quotes, product configuration rules make sure that all products have valid attributes and are compatible with other products in the offering.
-   **[Product Qualification Rules for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_product_qualification_rules.htm&language=en_US&type=5)**  
    Define customer eligibility for products to ensure that users see only specific products in the product catalog. You can qualify or disqualify products on the basis of criteria such as location, account attributes, or age.
-   **[Set Up Insurance Surcharges](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_surcharges.htm&language=en_US&type=5#insurance_admin_set_up_surcharges)**  
    Calculate applicable taxes and fees for Insurance quotes and policies by using surcharges.
-   **[Set up Insurance Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_quoting.htm&language=en_US&type=5#insurance_admin_set_up_quoting)**  
    Before you can start quoting, there are a few setup tasks that you must complete.
-   **[Set Up Exclusions and Clauses](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_exclusions.htm&language=en_US&type=5)**  
    To set up exclusions and clauses you use Constraint Builder to update the constraint model that defines the insurance product. From that model, you generate content text that you use to create specific clauses that can be automatically or manually added to quotes.
-   **[Constraint Rules Engine Adoption for Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator.htm&language=en_US&type=5)**  
    Adopt Constraint Rules Engine (CRE) for insurance quoting to validate complex product configurations with constraint-based logic. This feature is in beta and supports deeply nested bundles, cross-product dependencies, and multi-instance insurance scenarios. CRE ensures accurate quoting by preventing invalid selections while you transition from Business Rules Engine to a constraint-driven model.

Did this article solve your issue?

Let us know so we can improve!

YesNo