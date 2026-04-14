---
title: "Child Spec Inheritance with Product Classes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_child_spec_inheritance_with_product_classes_604322.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Child Spec Inheritance with Product Classes

Child Spec Inheritance with Product Classes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Child Spec Inheritance with Product Classes

Child spec inheritance, which includes coverages, insured items, insured parties, and rating facts, exists at two levels.

Whole child specs are inherited from the product class. You create a complete product class by adding child specs to it.

You can add new child specs to a product model that's based on a product class.

Attributes, attribute configuration, attribute rules, and attribute value rules on those child specs are inherited directly from the child specs, not from the product class.

You can make changes to attributes, attribute configuration, attribute rules, and attribute values directly on a product model that's based on a product class. Making a change like this creates an override of the original child spec.

Instead, you can override them on a single product model. Or you can make a change to the original child spec, and that change will be inherited by all the product models that use that child spec.

You cannot change any of these things on a product class.

Did this article solve your issue?

Let us know so we can improve!

YesNo