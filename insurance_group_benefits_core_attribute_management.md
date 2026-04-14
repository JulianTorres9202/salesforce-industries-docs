---
title: "Attribute Management for Group Benefits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_attribute_management.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Attribute Management for Group Benefits

Attribute Management for Group Benefits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attribute Management for Group Benefits

Attributes define the details of your group benefit products, such as age for members or deductible for coverages. Building attributes is a step-by-step process: first define reusable picklists, then create attributes, and finally organize them into categories. This approach keeps your model structured and reusable across products.

-   **[Define Attribute Picklists for Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_define_attribute_picklists.htm&language=en_US&type=5)**  
    Start by defining picklists that hold reusable sets of values. You reference these picklists later when you create attributes. For example, a Deductible attribute can pull values like $50, $100, $250. To use picklists with your attributes, define the picklists first before creating the attributes.
-   **[Create Attribute Definition for Insurance Products](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_define_product_attributes.htm&language=en_US&type=5)**  
    Once you have picklists, define attributes to capture the characteristics of your insurance products. Attributes represent the details you evaluate during quoting and configuration. For example, Deductible and Limit are attributes of a coverage, while Age and Gender are attributes of a member.
-   **[Organize Insurance Attributes with Categories](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_organize_attributes_with_categories.htm&language=en_US&type=5)**  
    Attribute categories are optional, but they help organize large sets of attributes into meaningful groups. For example, you can group First Name, Last Name, Age, Gender, and Marital Status under a category called Personal Information. This makes it easier to manage and assign attributes to product classifications.

Did this article solve your issue?

Let us know so we can improve!

YesNo