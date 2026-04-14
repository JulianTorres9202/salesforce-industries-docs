---
title: "Root Product Specs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Root Product Specs

Root Product Specs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Root Product Specs

Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.

Before You Begin

Wait! Before you put together a root product spec, complete these tasks:

-   Create attribute categories and product attributes. See [Product Attributes in Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_product_attributes_in_product_specs.htm&language=en_US&type=5 "Product attributes are key pieces of the whole Vlocity Insurance and Vlocity Health platform. They define coverages, insured items, and other parts of insurance products and health plans. They correspond to anything that's important to quoting, rating, and writing an insurance policy. Attributes include inputs to rating (pricing), and characteristics that define claims.").
    
-   Create child specs. See [Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").
    
-   Create product classes if you plan to use them. See [Working with Product Classes](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_product_classes_606568.htm&language=en_US&type=5 "Product classes act as templates for product models. After you create a product class, create products based on the class. These products inherit all the attributes, coverages, insured items, insured parties, rating facts, and rules from the product class. If you offer several variations of an insurance product, product classes can help you create those product models much more quickly.").
    

-   **[Create a Root Product Spec from Scratch](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_root_product_spec_from_scratch_605766.htm&language=en_US&type=5)**  
    When you create a root product spec from scratch, you start with a blank slate instead of creating a product model based on a product class or cloning an existing root product spec.
-   **[Set Up a Multi-Instance Hierarchy](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_a_multi_instance_hierarchy_606260.htm&language=en_US&type=5)**  
    When you create a multi-instance product model, you work with coverage specs, insured item specs, and insured party specs a little bit differently.
-   **[Create a Product Model Based on a Product Class](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_product_model_based_on_a_product_class_606311.htm&language=en_US&type=5)**  
    You can use a product class to create products faster and more easily. Product classes already contain specific coverages, insured items, insured parties, rating facts, root product attributes, and rules. After you set up product classes, you can use them as templates for root product specs.
-   **[Clone Products](https://help.salesforce.com/s/articleView?id=ind.insurance_clone_products_606465.htm&language=en_US&type=5)**  
    If you need to create a bunch of similar product models that contain many of the same child specs and attributes and rules, it's much quicker to clone and modify a product than it is to model each one from scratch.

Did this article solve your issue?

Let us know so we can improve!

YesNo