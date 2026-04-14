---
title: "Use Extended Attributes in Group Benefits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_extended_attributes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Use Extended Attributes in Group Benefits

Use Extended Attributes in Group Benefits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Use Extended Attributes in Group Benefits

Use extended attributes to pull values from other objects into products. For example, source a member’s first name, last name, age, gender, and smoker status from the Group Census Member object. This approach centralises data in obe object and reduces duplication across products.

-   **[Add Reference Objects for Extended Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_add_reference_objects.htm&language=en_US&type=5)**  
    Extended attributes use census objects to supply product attribute values dynamically. To enable this, first add the relevant census objects to the reference object picklist.
-   **[Configure Extended Attributes for Product Classifications or Products](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_update_configuration_in_product_classification.htm&language=en_US&type=5)**  
    If you want the attribute to have the same behavior across all products inheriting the product classification, update the configuration in product classification. For example, configure First Name and Last Name as extended attributes on the Member classification so that every product based on this classification automatically inherits them.
-   **[Create Extended Attributes for Reference Object IDs](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_extended_attributes_for_reference_object_ids.htm&language=en_US&type=5)**  
    For each extended attribute that you configure, create an additional extended attribute in the same product or product classification for the Id field of every unique sObject or custom object referenced in that configuration. For example, if you use the Contact and Group Census Member objects to reference the State and Age fields in the Member product classification, create two more extended attributes in the same classification, one for Contact and one for Group Census Member, to reference their Id fields.

Did this article solve your issue?

Let us know so we can improve!

YesNo