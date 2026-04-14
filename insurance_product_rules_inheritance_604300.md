---
title: "Product Rules Inheritance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_product_rules_inheritance_604300.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Product Rules Inheritance

Product Rules Inheritance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product Rules Inheritance

Product rules include eligibility rules and underwriting rules. When you set up product rules on a product class, all product models you create based on that product class inherit those rules.

You can't override inherited product rules on a product model. The inherited product rules will display but be grayed out. But you can add new, additional product rules to a root product spec associated with a product spec.

[](https://help.salesforce.com/s?language=en_US)

Instead, you must go back to the product class and make changes to the rules on the product class. These changes will be inherited by every product model that's based on this product class.

You can add new underwriting rules to a product model that's based on a product class. No inheritance applies if you add underwriting rules--the rules you add will apply only to that one product model.

You can't delete product rules that have been inherited from a product class.

Did this article solve your issue?

Let us know so we can improve!

YesNo