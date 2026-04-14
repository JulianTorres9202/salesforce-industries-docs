---
title: "Create Product Eligibility Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_product_eligibility_rules_607661.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Product Eligibility Rules

Create Product Eligibility Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Product Eligibility Rules

Insurance uses eligibility rules to help determine what insurance products and optional coverages a customer is eligible for. You can use eligibility rules in the quote process to screen out insurance products and optional coverages that a potential customer doesn't qualify for. For example, you can create an eligibility rule for a Medicare supplement insurance product that screens out anyone under the age of 65.

1.  On the insurance product page, click the **Rules** tab. (Or **More > Rules** if you can't see the **Rules** tab.)
2.  In the Expression field, enter a formula to create your eligibility rule or rules.
    
    To enter more than one eligibility rule, use `AND` or `OR` to separate the rules.
    
3.  (Optional) Enter a descriptive note about this rule. Click the bubble icon and enter text. The note saves automatically.
4.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)When this rule is invoked, the customer or agent sees only the available insurance products that meet this rule (the rule returns TRUE).

Did this article solve your issue?

Let us know so we can improve!

YesNo