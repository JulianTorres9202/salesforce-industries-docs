---
title: "Create the ID Extended Attribute"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_id_extended_attribute.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create the ID Extended Attribute

Create the ID Extended Attribute[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create the ID Extended Attribute

Whenever you configure an extended attribute from a field on a reference object, create an extended attribute for that object’s ID field on the same product or product classification.

The ID extended attribute is the only extended attribute that is not read-only.

For example, if you use Contact and Account objects to get the State and Age fields for the Driver product classification, you need extended attributes in the same product classification referring to the ID fields of those objects.

This extended attribute is used to render the Standard Lookup field in the configurator user-interface, containing all the available records available for selection from the reference object.

1.  Create an attribute definition of data type text. For the code, use the API name of the reference object.
2.  Associate the attribute to the product classification.
3.  Configure the attribute in the assigned attribute for product classification to update the reference object and reference field name, selecting the ID of the reference object.
    
    Note Ensure that you don't mark the field as read only, as it's used for multiple records that populate the standard lookup field during quote configuration.
    

#### See Also

-   [Dynamic Attributes](https://help.salesforce.com/s/articleView?id=ind.product_catalog_dynamic_attributes.htm&language=en_US&type=5)
-   [Create Product Attributes](https://help.salesforce.com/s/articleView?id=ind.product_catalog_dyn_create_attributes.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo