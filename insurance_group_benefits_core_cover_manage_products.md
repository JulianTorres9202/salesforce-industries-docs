---
title: "Manage Classifications and Products for Group Benefits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_cover_manage_products.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Manage Classifications and Products for Group Benefits

Manage Classifications and Products for Group Benefits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Manage Classifications and Products for Group Benefits

Product classifications and products define the structure of your group insurance model. A classification acts as a template to group attributes and make them reusable across products. Products represent the actual insurance plans and components that are bundled into your hierarchy. Together, they form the foundation of the group benefits product model.

-   **[Set Up Product Classifications in Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_product_classification.htm&language=en_US&type=5)**  
    Set up product classifications to group attributes and provide reusable templates. For example, you can create a GroupSummary classification to model group-level attributes like Total Members and Average Age.
-   **[Create Insurance Products for Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_model_create_products.htm&language=en_US&type=5)**  
    Create products for the Medical Platinum hierarchy. Root product is the top-level spec that defines an insurance product, such as a health, dental, or vision plan. It can include one or more group classes, members, and coverages.
-   **[Build the Group Benefits Product Structure](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_model_build_product_strcuture.htm&language=en_US&type=5)**  
    Once products are created, build the bundle hierarchy to connect them. This defines how the Medical Platinum plan expands into group classes, members, and coverages.
-   **[Assign Attributes to Insurance Product Classifications](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_assign_attributes_to_product_classifications.htm&language=en_US&type=5)**  
    After you create a product classification, assign attributes to it. Attributes define the information you want to capture at runtime. For example, the Member product classification uses the Basic Information category and Contact information. Assigning attributes ensures that every product inheriting the classification automatically carries these characteristics.
-   **[Configure Attributes for Insurance Products](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_configure_attributes_for_products.htm&language=en_US&type=5)**  
    Products inherit attributes from their classification, but you can override them at the product level.
-   **[Use Extended Attributes in Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_extended_attributes.htm&language=en_US&type=5)**  
    Use extended attributes to pull values from other objects into products. For example, source a member’s first name, last name, age, gender, and smoker status from the Group Census Member object. This approach centralises data in obe object and reduces duplication across products.

Did this article solve your issue?

Let us know so we can improve!

YesNo