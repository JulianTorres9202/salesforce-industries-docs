---
title: "Optional Coverage and Coverage Relationship Rules Inheritance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_and_coverage_relationship_rules_inheritance_604348.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Optional Coverage and Coverage Relationship Rules Inheritance

Optional Coverage and Coverage Relationship Rules Inheritance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Optional Coverage and Coverage Relationship Rules Inheritance

When you set up optional coverage rules and coverage relationship rules on a product class, all product models you create based on that product class inherit those rules.

You can't override inherited optional coverage rules or coverage relationship rules on a product model. The inherited rules will be displayed but grayed out.

You also can't add any optional coverage rules to a product model that's based on a product class.

You can't delete optional coverage rules that a product model inherited from a product class.

[](https://help.salesforce.com/s?language=en_US)

Instead, you must go back to the product class and make changes to the rules on the product class. These changes will be inherited by every product model that's based on this product class.

You can add optional coverage rules to product models if they don't exist on the product class, and so are not inherited.

Did this article solve your issue?

Let us know so we can improve!

YesNo