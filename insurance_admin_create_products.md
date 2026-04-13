---
title: "Create Products for Digital Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_products.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create Products for Digital Insurance

Create Products for Digital Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Products for Digital Insurance

Set up the insurance product classifications and products that define your offering.

1.  Use Product classifications to create multiple products that are similar yet different. For example, you can create and re-use a "Coverage" product classification for multiple products like Collision, Comprehensive, and Disability coverages. Product classifications enable you to associate attributes with products. A product inherits the attributes of its product classification. You can override the attributes as needed. See [Create a Product Classification](https://help.salesforce.com/s/articleView?id=ind.product_catalog_create_a_product_classification.htm&language=en_US&type=5).
2.  Create simple and bundled products.
    -   To create simple products such as Collision and Comprehensive coverage products, see [Create Simple Products](https://help.salesforce.com/s/articleView?id=ind.product_catalog_create_simple_products.htm&language=en_US&type=5).
    -   To create a more complex product such as an insured item, see [Create Bundled Products](https://help.salesforce.com/s/articleView?id=ind.product_catalog_create_bundled_products.htm&language=en_US&type=5). For example, a product like Auto is composed of the Driver product classification as well as one or more coverage products.
    -   To organize products that are composed of other pr see [Create a Bundled Product Structure](https://help.salesforce.com/s/articleView?id=ind.product_catalog_creation_of_a_bundled_product_structure.htm&language=en_US&type=5).
3.  Assign attributes to each product classification. You can assign individual attributes individually or by category. For example, you might assign the product classification “Driver” an attribute category “Personal Information,” which contains attributes such as “First Name,” “Age,” and “Contact Information.” In turn, “Contact Information” might be an attribute category containing attributes like “E-mail” and “Phone Number.” See [Assign Attributes to a Product Classification](https://help.salesforce.com/s/articleView?id=ind.product_catalog_assign_attributes_to_a_product_classification.htm&language=en_US&type=5#product_catalog_assign_attributes_to_a_product_classification) and [Include or Exclude Picklist Values in a Product Classification…](https://help.salesforce.com/s/articleView?id=ind.product_catalog_include_or_exclude_picklist_values_in_a_product_classification_attribute.htm&language=en_US&type=5)
4.  Customize each product’s attribute values. See [Configure Product Attributes in Revenue Cloud](https://help.salesforce.com/s/articleView?id=ind.product_catalog_configure_product_attributes.htm&language=en_US&type=5).
    
    Note You can’t associate an attribute with a product or bundle unless the attribute is part of the product classification.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo