---
title: "Build Insurance Product Models"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_product_models_603786.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Build Insurance Product Models

Build Insurance Product Models[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Build Insurance Product Models

An insurance product model is a structured definition of a product that a company sells, then services. A product model acts as a blueprint for an insurance product.

At runtime, Insurance services use the product model to create an instance of an insurance or health product. Quotes and policies contain the runtime instance that the services create.

[](https://help.salesforce.com/s?language=en_US)

## What's in a Product Model

An insurance product model contains the following building blocks:

-   [Specifications](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_modeling_specifications_603842.htm&language=en_US&type=5 "Specifications are the basic blocks that build an insurance product model. We call them specs for short.")
    
    [](https://help.salesforce.com/s?language=en_US)Specifications are the basic blocks that build an insurance or health product model. We call them specs for short.
    
-   [Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_modeling_attributes_604071.htm&language=en_US&type=5 "Attributes are the building blocks of specifications. They define the details of the data that's included in insurance and health products.")
    
    [](https://help.salesforce.com/s?language=en_US)Attributes are the building blocks of specifications. They define the details of the data that's included in insurance and health products.
    
-   [Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_modeling_rules_604104.htm&language=en_US&type=5 "Rules define how an insurance or health product behaves.")
    
    [](https://help.salesforce.com/s?language=en_US)Rules define how an insurance or health product behaves.
    

Not every product you model will include all of these building blocks--in fact, many products won't include all of them.

Your product models will be unique to the needs of your business.

[](https://help.salesforce.com/s?language=en_US)

## What's Next

Now that you're familiar with product modeling, go on to start creating product models of your own.

-   **[Insurance Product Modeling Specifications](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_modeling_specifications_603842.htm&language=en_US&type=5)**  
    Specifications are the basic blocks that build an insurance product model. We call them specs for short.
-   **[Insurance Product Modeling Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_modeling_attributes_604071.htm&language=en_US&type=5)**  
    Attributes are the building blocks of specifications. They define the details of the data that's included in insurance and health products.
-   **[Insurance Product Modeling Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_modeling_rules_604104.htm&language=en_US&type=5)**  
    Rules define how an insurance or health product behaves.
-   **[Insurance Product Inheritance](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_inheritance_604117.htm&language=en_US&type=5)**  
    Insurance product modeling includes two levels of inheritance: child spec inheritance and product class inheritance. By using inheritance, you can cut down the amount of time you spend individually creating every product model in your product catalog.
-   **[Product Attributes in Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_product_attributes_in_product_specs.htm&language=en_US&type=5)**  
    Product attributes are key pieces of the whole Vlocity Insurance and Vlocity Health platform. They define coverages, insured items, and other parts of insurance products and health plans. They correspond to anything that's important to quoting, rating, and writing an insurance policy. Attributes include inputs to rating (pricing), and characteristics that define claims.
-   **[Child Specs for Root Products](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5)**  
    Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.
-   **[Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5)**  
    Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.
-   **[Working with Product Classes](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_product_classes_606568.htm&language=en_US&type=5)**  
    Product classes act as templates for product models. After you create a product class, create products based on the class. These products inherit all the attributes, coverages, insured items, insured parties, rating facts, and rules from the product class. If you offer several variations of an insurance product, product classes can help you create those product models much more quickly.
-   **[Insurance Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_rules_606729.htm&language=en_US&type=5)**  
    Rules define the way Insurance products behave when those products are quoted, sold, and serviced.
-   **[Taxes and Fees](https://help.salesforce.com/s/articleView?id=ind.insurance_taxes_and_fees_608285.htm&language=en_US&type=5)**  
    Calculate applicable taxes on Vlocity Insurance quotes and policies, and applicable fees on Vlocity Health and Vlocity Insurance quotes and policies.
-   **[Cloning Products](https://help.salesforce.com/s/articleView?id=ind.insurance_cloning_products_608575.htm&language=en_US&type=5)**  
    When you've got a bunch of similar products to create, it's a lot easier to create only the first one from scratch. Then you can clone it and make the minor changes you need to the cloned product.
-   **[Create Custom Numbering](https://help.salesforce.com/s/articleView?id=ind.insurance_create_custom_numbering.htm&language=en_US&type=5)**  
    Insurance generates a unique number for each new insurance policy, claim, census, and other items as they're created.
-   **[Configure and Use Trailing Documents Requirements](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_and_use_trailing_documents_requirements.htm&language=en_US&type=5)**  
    Enrich your org's data by giving Vlocity and Community users the ability to upload documents associated with government, insurance, and health plan objects. For example, let underwriters for property insurance upload required survey and inspection documentation. Let customers applying for life insurance upload required medical test results.
-   **[Attribute Rules and Attribute Value Rules Structure for Batch Loading](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_rules_and_attribute_value_rules_structure_for_batch_loading_609161.htm&language=en_US&type=5)**  
    If you have to add attribute rules or attribute value rules to hundreds or thousands of products, you can write scripts to batch load rules directly into the database.
-   **[Eligibility Rules Structure for Batch Loading](https://help.salesforce.com/s/articleView?id=ind.insurance_eligibility_rules_structure_for_batch_loading_609321.htm&language=en_US&type=5)**  
    If you have to add eligibility rules at the root product level or at the optional coverage level to hundreds or thousands of products, you can write scripts to batch load rules directly into the database.
-   **[Policy Product Management Definitions](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_product_management_definitions_609335.htm&language=en_US&type=5)**  
    Vlocity Insurance provides a robust administration environment to model and administer a wide range of insurance products. Correctly structuring products ensures consistent enforcement of pricing and rules throughout the policy lifecycle and reduces the effort of maintaining a large set of products.
-   **[Product JSON Structure Model](https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5)**  
    The product JSON object provides a portable product data object for runtime use between services and templates.

Did this article solve your issue?

Let us know so we can improve!

YesNo