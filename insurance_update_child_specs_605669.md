---
title: "Update Child Specs"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_update_child_specs_605669.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Update Child Specs

Update Child Specs[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Update Child Specs

Over time, you can tweak your child specs. After you make changes to the attributes and attribute values in a child spec, use the Push Attribute action to push those changes out to the instances of the child spec in other products.

Before You Begin

Make sure that the Push Attribute action is available on the Product page. See [Add the Push Attribute Action to the Product Page](https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_push_attribute_action_to_the_product_page_605640.htm&language=en_US&type=5 "If you update a child spec, you can use the Push Attribute action to push your changes out to the instances of the child spec in other products.").

[](https://help.salesforce.com/s?language=en_US)For example, an auto insurance carrier has a child spec called Deductible that's used by all their auto insurance products. The insurance carrier adds a new value, $250, to this coverage spec. Then they push that value out to the instances of Deductible in all their auto insurance products.

1.  Go to the child spec record page.
2.  Go to the **Attributes** tab.
3.  Make changes. For example, add a new attribute or add, modify, or delete the values in an existing attribute.
4.  Click **Save** for a new attribute or click **Update** for a modified attribute.
5.  Choose the **Push Attribute** page action, then click **Continue**.
    
    The window tells you how many instances of this child spec are affected by the push.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo