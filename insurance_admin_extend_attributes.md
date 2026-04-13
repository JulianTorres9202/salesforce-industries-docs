---
title: "Configure Product Classification Attributes to Be Extended Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_extend_attributes.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Configure Product Classification Attributes to Be Extended Attributes

Configure Product Classification Attributes to Be Extended Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Product Classification Attributes to Be Extended Attributes

To make an extended attribute available across products in the same classification, update the product classification. For example, you can add the member first name and last name as extended attributes for all the products inheriting the product classification “Driver.”

1.  In **Product Catalog Management**, select the product classification where you want to create the extended attribute.
2.  Navigate to the **Attributes** tab.
3.  To configure an assigned attribute, click its arrow and then click **Edit**. Make sure you choose an attribute with the same data type as the reference field you plan to use.
4.  Select the reference object that will provide the value for the attribute. For example, select the Contact object to get the First Name.
    
    The list of available fields appears in the Reference Field on the selected object.
    
5.  Select the field that provides the attribute value.
6.  Mark the field as read-only. Because the value will be fetched from the reference object and field, you can’t update it.
7.  Save your work.

Did this article solve your issue?

Let us know so we can improve!

YesNo