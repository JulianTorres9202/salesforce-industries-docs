---
title: "Create Attribute Value Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_attribute_value_rules_608112.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Attribute Value Rules

Create Attribute Value Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Attribute Value Rules

Use Attribute Value Rules to determine if and when an attribute value is visible to users.

Attribute value rules are only applicable for attributes that have multiple discrete values, like currency and text dropdowns. Attribute Value Rules apply to a specific value on one attribute.

You can create the following types of attribute value rules:

[](https://help.salesforce.com/s?language=en_US)

-   Hide
    
    Hides this attribute value from users if the rule evaluates to true.
    

The color of the Rules icon indicates whether a rule has been applied to an attribute. If the Rules icon next to the attribute value is black, there are no rules defined. If the Rules icon is blue, one or more rules are assigned to the attribute value.

1.  Click the Rules icon on your attribute value.
2.  Click the **Add a Rule** link.
3.  In the **Type** field, choose **Hide**.
4.  Enter the rule in the **Expression** field.
    
    [](https://help.salesforce.com/s?language=en_US)For example, you want to hide an attribute value of $40 when the value of the Copay attribute (a different attribute in this product) equals 40.
    
    [](https://help.salesforce.com/s?language=en_US)Use the % character to create variables. The formula for this example looks like this:
    
    [](https://help.salesforce.com/s?language=en_US)`%productCode.attributeCode%="40"`.
    
    [](https://help.salesforce.com/s?language=en_US)If the Product Code for the Large Group Health product is `LGH`and the Attribute Code for Copay is `copay`, the code in the expression looks like this:
    
    [](https://help.salesforce.com/s?language=en_US)When the rule evaluates to true, the $40 attribute value is hidden from users.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo