---
title: "Group Voluntary Benefits Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_voluntary_benefits_product_model_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Voluntary Benefits Product Model

Group Voluntary Benefits Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Voluntary Benefits Product Model

To get the most out of the Group Voluntary Benefits Application, you need to understand how it's built. So read on to learn more about its product model.

The product model underpins all the business processes used in the Group Voluntary Benefits line of business. It has the products:

-   Member Based: Medical, Vision, Dental, Critical Illness
    
-   Summary Based: Dental Summary
    

Here's the high-level product model for the Critical Illness root product:

Read on for the components of member-based and summary-based products.

[](https://help.salesforce.com/s?language=en_US)

## Coverages

The spec that models a coverage provided as part of an insurance or health product. The coverage spec defines the required and optional coverages on an insurance product.

To learn about the coverage specs for member-based products, see [Coverages for Member-based Products](https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_for_member-based_products.htm&language=en_US&type=5 "The spec that models a coverage provided as part of an insurance or health product. The coverage spec defines the required and optional coverages on an insurance product.").

To learn about the coverage specs for summary-based products, see [Coverages for Summary-Based Products](https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_for_summary_based_products.htm&language=en_US&type=5 "The spec that models a coverage provided as part of an insurance or health product. The coverage spec defines the required and optional coverages on an insurance product.")

[](https://help.salesforce.com/s?language=en_US)

## Rating Facts

The spec that contains attributes used to rate an insurance or health product. The attributes in a rating fact spec are data needed to rate a product, but aren't stored with the product. Rating fact spec data is often pulled from other parts of Vlocity, such as Account, Census, Census Member or from third-party systems.

The `TransformCensusMemberRatingFactsStd` Omnistudio Data Mapper is used to transform data from objects, such as account, census, census member to the corresponding rating fact attributes.

[](https://help.salesforce.com/s?language=en_US)

## Attributes

Attributes are the building blocks of specifications. They define the details of the data that's included in products. All the attributes used in the member-based and summary-based product models and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.

The attribute's value data type, available values, default selected value, rating status, and other specifics are configured on the coverage spec or root product spec. Attributes are further arranged into Attribute Categories.

-   **[Group Voluntary Benefits Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_group_voluntary_benefits_attribute_catalog_omnistudio.htm&language=en_US&type=5)**  
    All attributes used for the Group Voluntary Benefits line of business are listed by Attribute Category. Each Attribute Category has its own table, which includes attribute codes and the product specs the attributes are used by.
-   **[Coverages for Member-based Products](https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_for_member-based_products.htm&language=en_US&type=5)**  
    The spec that models a coverage provided as part of an insurance or health product. The coverage spec defines the required and optional coverages on an insurance product.
-   **[Coverages for Summary-Based Products](https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_for_summary_based_products.htm&language=en_US&type=5)**  
    The spec that models a coverage provided as part of an insurance or health product. The coverage spec defines the required and optional coverages on an insurance product.

Did this article solve your issue?

Let us know so we can improve!

YesNo