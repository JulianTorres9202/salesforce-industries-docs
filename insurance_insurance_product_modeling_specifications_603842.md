---
title: "Insurance Product Modeling Specifications"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_modeling_specifications_603842.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Product Modeling Specifications

Insurance Product Modeling Specifications[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Product Modeling Specifications

Specifications are the basic blocks that build an insurance product model. We call them specs for short.

[](https://help.salesforce.com/s?language=en_US)Each spec is also a record type of the Salesforce Product object.

[](https://help.salesforce.com/s?language=en_US)

-   Root product spec
    
    The top-level spec that defines a whole insurance or health product. It includes one or more of the other kinds of specs.
    
    Record type = Product
    
-   Insured item spec
    
    The spec that models a piece of property that a product will insure. Some examples of insured items include vehicles, boats, and homes.
    
    Record type = Insured Item Spec
    
    Not all insurance and health product models include insured items. For example, health product models almost always don't have insured items.
    
    An insured item spec can be a child of a root product spec. It can also be a child of another insured item spec (making it a grandchild).
    
-   Insured party spec
    
    The spec that models a person that a product will insure.
    
    Record type = Insured Party Spec
    
    Not all insurance and health products include insured party specs. Auto insurance products and life insurance products typically include insured party specs. Business insurance products typically don't have insured party specs.
    
    An insured party spec can be a child of a root product spec. It can also be a child of an insured item spec (making it a grandchild).
    
-   Coverage spec
    
    The spec that models a coverage provided as part of an insurance or health product. A typical auto insurance coverage is Collision. A typical health coverage is Office Visit.
    
    Record type = Coverage Spec
    
    Insurance and health products almost all include at least one coverage spec.
    
-   Rating fact spec
    
    A spec that contains attributes used to rate an insurance or health product. The attributes in a rating fact spec are data needed to rate a product but aren't stored with the product. Rating fact spec data is often pulled from other records in Insurance, such as a Claim or Census record, or from third-party systems.
    
    Record type = Rating Fact Spec
    

[](https://help.salesforce.com/s?language=en_US)

## Product Classes

Product class specs act as templates for product models. You can create product classes that contain most of the specs and rules a group of products will have.

A product class can contain coverages, insured items, insured parties, rating facts, eligibility rules, underwriting (workflow) rules, and details. Most of these will be inherited by all product models that you created based on this class.

Record type = Class

To learn a lot more about how to use product classes, see [Working with Product Classes](https://help.salesforce.com/s/articleView?id=ind.insurance_creating_product_classes_606568.htm&language=en_US&type=5 "Product classes act as templates for product models. After you create a product class, create products based on the class. These products inherit all the attributes, coverages, insured items, insured parties, rating facts, and rules from the product class. If you offer several variations of an insurance product, product classes can help you create those product models much more quickly.").

[](https://help.salesforce.com/s?language=en_US)

## Inheritance

Inheritance works at two levels in Insurance product models:

-   Product models inherit configuration from product classes
    
-   Coverages, insured items, insured parties, and rating facts on root products inherit configuration from their corresponding specs
    

To learn much more about how inheritance works, see [Insurance Product Inheritance](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_product_inheritance_604117.htm&language=en_US&type=5 "Insurance product modeling includes two levels of inheritance: child spec inheritance and product class inheritance. By using inheritance, you can cut down the amount of time you spend individually creating every product model in your product catalog.").

[](https://help.salesforce.com/s?language=en_US)

## Single Instance and Multi-Instance Product Models

How you model any given insurance or health product depends on how you rate, quote, and sell that product, how your users buy that product, how data flows from the product model to the quote and the policy, and how claims data is handled and processed. Use the single instance product model for insurance products that have only one instance of any given insured item or insured party. Use the multi-instance product model for insurance products that can have more than one instance of their insured items or insured parties.

-   **[Single Instance Products](https://help.salesforce.com/s/articleView?id=ind.insurance_single_instance_products_603913.htm&language=en_US&type=5)**  
    A single instance insurance product model describes an insurance product that has only one instance of any given insured item (or insured party). For example, at runtime, a simple renter's insurance product allows only one instance of an insured item.
-   **[Multi-Instance Products](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_instance_products_603934.htm&language=en_US&type=5)**  
    A multi-instance insurance product model describes an insurance product that can have more than one instance of its insured items (or insured parties). Each insured item (or insured party) can also have its own set of coverage selections and attribute values.

Did this article solve your issue?

Let us know so we can improve!

YesNo