---
title: "Multi Auto Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_product_model_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multi Auto Product Model

Multi Auto Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multi Auto Product Model

The Multi Auto product is a multi-instance product model that lets users create quotes for multiple vehicles driven by multiple drivers. This product model has the flexibility to handle complex combinations, such a quote that's got three vehicles and four drivers who aren't all associated to the same vehicles.

-   **[Insured Item: Vehicle](https://help.salesforce.com/s/articleView?id=ind.insured_item_vehicle_omnistudio.htm&language=en_US&type=5)**  
    The Insured Item Spec is the spec for vehicles to be insured.
-   **[Insured Party: Driver](https://help.salesforce.com/s/articleView?id=ind.insured_party__driver_omnistudio.htm&language=en_US&type=5)**  
    The insured party spec represents drivers for an auto insurance product. It's a child of the Insured Item spec.
-   **[Coverages for Auto Products](https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_for_auto_products_omnistudio.htm&language=en_US&type=5)**  
    Coverage specs define the required and optional coverages on an insurance product. On the Product page, the Product Record Type at the top left of the page = Coverage Spec.
-   **[Multi Auto Root Product](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_auto_root_product_omnistudio.htm&language=en_US&type=5)**  
    The root product spec is the container for the Multi Auto product model. The system uses the data stored in this product model in downstream business processes, including quoting, issuing policies, and adjudicating claims.
-   **[Attributes for Auto Products](https://help.salesforce.com/s/articleView?id=ind.insurance_attributes_for_auto_products_with_omnistudio.htm&language=en_US&type=5)**  
    All the attributes used in the Auto insurance product and the insured item spec, insured party spec, and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.
-   **[Rules for Auto Products](https://help.salesforce.com/s/articleView?id=ind.insurance_rules_for_auto_products_omnistudio.htm&language=en_US&type=5)**  
    The Multi Auto product includes a number of rules.
-   **[Surcharges for Auto Products](https://help.salesforce.com/s/articleView?id=ind.insurance_surcharges_for_auto_products_omnistudio.htm&language=en_US&type=5)**  
    The Multi Auto insurance root product includes several surcharges set up to be calculated when quotes are created and policies are modified.
-   **[Simulate Rating the Multi Auto Product](https://help.salesforce.com/s/articleView?id=ind.insurance_simulate_rating_the_multi_auto_product_omnistudio.htm&language=en_US&type=5)**  
    The Simulate tab on the root product spec has the ratings set up to simulate rating the Multi Auto product model.

Did this article solve your issue?

Let us know so we can improve!

YesNo